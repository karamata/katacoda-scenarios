# Bài 4
Đảo ngược chuỗi sử dụng vòng lặp và đệ quy. 

Gợi ý: Sử dụng StringBuilder hoặc StringBuffer để dễ dàng thao tác hơn, tránh sử dụng String ví nó có tính chất immutable việc thao tác trên chúng sẽ khiến nó tạo thêm một String mới gây hao tổn bộ nhớ. 


Các bạn mở file `Excersize4.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```
    
        public class Excersize4 {

            public static void main(String[] args) {
                System.out.println("1".substring(1));
                //original string
                String str = "Sony is going to introduce Internet TV soon";
                System.out.println("Original String: " + str);

                //reversed string using Stringbuffer
                String reverseStr = new StringBuffer(str).reverse().toString();
                System.out.println("Reverse String in Java using StringBuffer: " + reverseStr);

                //iterative method to reverse String in Java
                reverseStr = reverse(str);
                System.out.println("Reverse String in Java using Iteration: " + reverseStr);

                //recursive method to reverse String in Java
                reverseStr = reverseRecursively(str);
                System.out.println("Reverse String in Java using Recursion: " + reverseStr);


            }

            public static String reverse(String str) {
                StringBuilder strBuilder = new StringBuilder();
                char[] strChars = str.toCharArray();

                for (int i = strChars.length - 1; i >= 0; i--) {
                    strBuilder.append(strChars[i]);
                }

                return strBuilder.toString();
            }

            public static String reverseRecursively(String str) {

                //base case to handle one char string and empty string
                if (str.length() < 2) {
                    return str;
                }

                return reverseRecursively(str.substring(1)) + str.charAt(0);

            }

        }

    ```
</details>