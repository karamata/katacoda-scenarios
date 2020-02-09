# Bài 2
Tìm xem có bao nhiêu chuỗi xen kẽ từ 2 chuỗi cho trước. Giả sử rằng các ký tự trong 2 chuỗi là khác nhau.

Ví dụ cho hai chuỗi “WX” và “YZ” thì các chuỗi có thể tạo nên là: YWZX, WYZX, YWXZ, WXYZ, YZWX, WYXZ.

Gợi ý: Sử dụng đệ quy bóc tách từng ký tự trong từng chuỗi ra và thử vào chuỗi kết quả. 

[interleavings string](./interleavings-string-1024x672.jpg)


Các bạn mở file `Excersize13.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```
        import java.util.HashSet;
        import java.util.Set;


        public class Excersize13 {

            public static void main(String[] args) {
                String P = "WX";
                String Q = "YZ";
                System.out.println("The given strings are: " + P + "  " + Q);
                System.out.println("The interleavings strings are: ");
                Set<String> out = new HashSet<>();
                allInterleavings("", P, Q, out);

                out.stream().forEach(System.out::println);

            }

            public static void allInterleavings(String res, String P, String Q, Set<String> out) {
                System.out.println(P + " - " + Q + " - " + res);
                if (P.length() == 0 && Q.length() == 0) {
                    out.add(res);
                    return;
                }
                if (P.length() > 0) {
                    allInterleavings(res + P.charAt(0), P.substring(1), Q, out);
                }
                if (Q.length() > 0) {
                    allInterleavings(res + Q.charAt(0), P, Q.substring(1), out);
                }
            }


        }

    ```
</details>