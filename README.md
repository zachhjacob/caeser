package com.byaj;

import java.lang.String;
import java.util.Scanner;

    public class Main {
    public static StringBuffer encrypt(String text, int k) {

        StringBuffer result = new StringBuffer();

        for (int i = 0; i < text.length(); i++) {
            if (Character.isUpperCase(text.charAt(i))) {
                char ch = (char) (((int) text.charAt(i) +
                        k - 65) % 26 + 65);
                result.append(ch);
            } else {
                char ch = (char) (((int) text.charAt(i) +
                        k - 97) % 26 + 97);
                result.append(ch);
            }
        }
        return result;
    }


    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("PlainText: ");
        String text = in.nextLine();
        System.out.print("Provide an Integer for Number of rotations: ");
        int k = in.nextInt();
        System.out.println("Ciphertext: " + encrypt(text,k) );

    }
}
