# Bài 2
Viết chương trình in tất cả các chuỗi có thể có từ các ký tự của một chuỗi cho trước.

Ví dụ: “PQR” => PPP PPQ PPR PQP PQQ PQR PRP PRQ PRR QPP QPQ QPR QQP QQQ QQR QRP QRQ QRR RPP RPQ RPR RQP RQQ RQR RRP RRQ RRR. 

Gợi ý sử dụng đệ quy theo quy tắc sau

`<br />/**<br /> * PQR P<br /> * I = 0 =><br /> *      PQR PP I=0 PQR PPP<br /> *      PQR PP I=1 PQR PPQ<br /> *      PQR PP I=2 PQR PPR<br /> * I = 1 =><br /> *      PQR PQ I=0 PQR PQP<br /> *      PQR PQ I=1 PQR PQQ<br /> *      PQR PQ I=2 PQR PQR<br /> */`


Các bạn mở file `Excersize16.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize16 {
            public static void main(String[] args) {
                permutationWithRepeation("PQR");

            }

            private static void permutationWithRepeation(String str1) {
                System.out.println("The given string is: PQR");
                System.out.println("The permuted strings are:");
                showPermutation(str1, "");
            }

            private static void showPermutation(String str, String newStr) {
                if (newStr.length() == str.length()) {
                    System.out.println(newStr);
                    return;
                }
                for (int i = 0; i < str.length(); i++) {
                    showPermutation(str, newStr + str.charAt(i));
                }
            }

        }

    ```
</details>