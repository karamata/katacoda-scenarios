# Bài 12
Tìm substring palindrome dài nhất trong một chuỗi cho trước. Biết rằng chuỗi palindrome là chuỗi sau khi đảo ngược và chuỗi ban đầu giống nhau.


Các bạn mở file `Excersize12.java` và tự code thử đi nha, xong rồi biên dịch và chạy thử

<details>
    <summary>Lời giải</summary>
    ```

        public class Excersize12 {
            static int max (int x, int y) { return (x > y)? x : y; }

            static int lps(String seq) {
                int n = seq.length();
                int i, j, cl;
                int L[][] = new int[n][n];

                for (i = 0; i < n; i++)
                    L[i][i] = 1;

                for (cl=2; cl<=n; cl++)
                {
                    for (i=0; i<n-cl+1; i++)
                    {
                        j = i+cl-1;
                        if (seq.charAt(i) == seq.charAt(j) && cl == 2)
                            L[i][j] = 2;
                        else if (seq.charAt(i) == seq.charAt(j))
                            L[i][j] = L[i+1][j-1] + 2;
                        else
                            L[i][j] = max(L[i][j-1], L[i+1][j]);
                    }
                }

                return L[0][n-1];
            }


            public static void main(String[] args) {
                String seq = "GEEKSFORGEEKS";
                int n = seq.length();
                System.out.println("The lnegth of the lps is "+ lps(seq));

            }

        }

    ```
</details>