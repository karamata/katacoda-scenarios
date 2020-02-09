# Bài 2
Đếm số lượng ký tự nguyên âm và phụ âm xuất hiện trong chuỗi. Ví dụ chuỗi “java” có 2 nguyên âm “a” và 2 phụ âm “j” và “v”.

Gợi ý: Dùng switch case để đếm số lượng ký tự nguyên âm. Số phụ âm sẽ là độ dài của chuỗi trừ cho số lượng phụ âm.


Các bạn mở file `Excersize6.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize6 {

            public static void main(String[] args) {
                countVowels("java");
                countVowels("share");

            }

            public static void countVowels(String str) {
                char[] chars = str.toCharArray();
                int count = 0;
                for (char c : chars) {
                    switch (c) {
                        case 'a':
                        case 'e':
                        case 'i':
                        case 'o':
                        case 'u':
                            count++;
                            break;
                    }
                }

                System.out.println("Nguyen am cua : " + str + ": " + count);

                System.out.println("Phu am cua: " + str + ": " + (str.length() - count));
            }


        }

    ```
</details>