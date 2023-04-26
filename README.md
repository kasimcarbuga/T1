# T1


using System;

public class Program {
    public static void Main() {
        string input1 = "The weather is so sunny nowadays";
        string input2 = "Life is so beautiful";
        
        string output1 = ReverseStringWithoutWords(input1);
        string output2 = ReverseStringWithoutWords(input2);
        
        Console.WriteLine(output1);
        Console.WriteLine(output2);
    }
    
    public static string ReverseStringWithoutWords(string input) {
        char[] charArray = input.ToCharArray();
        Array.Reverse(charArray);
        int start = 0;
        for (int i = 0; i < charArray.Length; i++) {
            if (charArray[i] == ' ' || i == charArray.Length - 1) {
                if (i == charArray.Length - 1) {
                    i++;
                }
                int end = i - 1;
                while (start < end) {
                    char temp = charArray[start];
                    charArray[start] = charArray[end];
                    charArray[end] = temp;
                    start++;
                    end--;
                }
                start = i + 1;
            }
        }
        return new string(charArray);
    }
}
