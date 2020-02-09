# Bài 15
Viết chương trình tìm ký tự xuất hiện nhiều thứ 2 trong chuỗi. Nếu nhiều ký tự thoả thì in bất kỳ ký tự nào. Không phân biệt chữ hoa với chữ thường.

Ví dụ: “Successes” => “c”

Gợi ý: Khai báo mảng int [256] tương ứng với số lượng ký tự có thể có. Duyệt chuỗi với mỗi lần xuất hiện thì tăng lên 1 tại [str.charAt[i]]. Sau khi đã có số lần xuất hiện thì chỉ việc so sánh và lấy lý tự xuất hiện nhiều thứ nhì bằng nhiều cách như sắp xếp, duyệt etc


Các bạn mở file `Excersize15.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize15 {

            static final int NOOFCHARS = 256;

            static char get2ndMostFreq(String str) {

                str = str.toLowerCase();

                if (str == null) {
                    return '\0';
                }

                // create array int with default value is 0
                int[] ctr = new int[NOOFCHARS];
                int i;
                for (i = 0; i < str.length(); i++)
                    ctr[str.charAt(i)]++;
                System.out.println(ctr);

                int ctr_first = 0, ctr_second = 0;
                for (i = 0; i < NOOFCHARS; i++) {
                    if (ctr[i] > ctr[ctr_first]) {
                        ctr_second = ctr_first;
                        ctr_first = i;
                    } else if (ctr[i] > ctr[ctr_second] && ctr[i] != ctr[ctr_first])
                        ctr_second = i;
                }
                return (char) ctr_second;
            }

            public static void main(String args[]) {
                String str = "successes";
                System.out.println("The given string is: " + str);
                char res = get2ndMostFreq(str);
                if (res != '\0')
                    System.out.println("The second most frequent char in the string is: " + res);
                else
                    System.out.println("No second most frequent character found in the string.");
            }

        }

    ```
</details>