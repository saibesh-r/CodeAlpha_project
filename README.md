# CodeAlpha_project

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class WordCounterApp {
    public static void main(String[] args) {
        // Create the frame
        JFrame frame = new JFrame("Word Counter");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 300);
        frame.setLayout(new BorderLayout());

        // Create a text area for input
        JTextArea textArea = new JTextArea();
        JScrollPane scrollPane = new JScrollPane(textArea);
        frame.add(scrollPane, BorderLayout.CENTER);

        // Create a button to count words
        JButton countButton = new JButton("Count Words");
        frame.add(countButton, BorderLayout.SOUTH);

        // Create a label to display the result
        JLabel resultLabel = new JLabel("Word Count: 0");
        frame.add(resultLabel, BorderLayout.NORTH);

        // Add action listener to the button
        countButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String text = textArea.getText().trim();
                int wordCount = countWords(text);
                resultLabel.setText("Word Count: " + wordCount);
            }
        });

        // Make the frame visible
        frame.setVisible(true);
    }

    // Method to count words in a string
    private static int countWords(String text) {
        if (text.isEmpty()) {
            return 0;
        }
        String[] words = text.split("\\s+"); // Split by whitespace
        return words.length;
    }
}
