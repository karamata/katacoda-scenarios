# Bài 9
Đảo ngược các ký tự của chuỗi cách nhau bởi dấu cách mà không dùng thư viện. Ví dụ “I am developer ” => “developer am I”. Các ký tự bên trong chỉ cách nhau đúng một dấu khoảng cách.

Gợi ý: Các bạn cần loại bỏ dấu cách ở đầu và cuối câu, thao tác cắt chuỗi theo dấu cách và dùng StringBuilder hoặc StringBuffer để nối chuỗi.


Các bạn mở file `Excersize9.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize9 {

            public static void main(String[] args) {
                System.out.println(reverseWord1("I am developer"));

                System.out.println(reverseWord1(" I am gay "));

                System.out.println(reverseWord1("java is the best "));

                System.out.println(reverseWord1(""));
                System.out.println(reverseWord1(null));


                System.out.println("-------------------------------------");

                System.out.println(reverseWord2("I am developer"));

                System.out.println(reverseWord2(" I am gay "));

                System.out.println(reverseWord2("java is the best "));

            }

            public static String reverseWord1(String sentence) {
                    if (sentence == null || sentence.isEmpty()) {
                        return "";
                    }
                    List<String> words = Arrays.asList(sentence.split("\\s"));
                    StringBuilder sb = new StringBuilder(sentence.length());

                    for (int i = words.size() - 1; i >= 0; i--) {
                        sb.append(words.get(i));
                        sb.append(' ');
                    }

                    return sb.toString().trim();
                }

                public static String reverseWord2(String line) {
                    if (line.trim().isEmpty()) {
                        return line;
                    }

                    StringBuilder reverse = new StringBuilder();
                    String[] sa = line.trim().split("\\s");

                    for (int i = sa.length - 1; i >= 0; i--) {
                        reverse.append(sa[i]);
                        reverse.append(' ');
                    }

                    return reverse.toString().trim();
                }


        }

    ```
</details>