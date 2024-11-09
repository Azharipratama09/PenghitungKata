# PenghitungKata
 Tugas 5-Muhammad Azhari Nur Pratama-2210010326
## 1. Deskripsi Program:
• Gunakan JTextArea dalam JScrollPane untuk input teks
• Setelah menekan tombol Hitung, hasil perhitungan berupa jumlah
kata dan karakter ditampilkan pada beberapa JLabel

## 2. Komponen GUI:
JFrame, JPanel, JLabel, JTextArea, JScrollPane, JButton
## 3. Logika Program: 
Manipulasi string, Ekspresi reguler
## 4. Events:
• ActionListener untuk tombol Hitung
~~~
    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
       jButton1.addActionListener((ActionEvent e) -> {
        hitungText(); // Memanggil metode countText() ketika tombol ditekan
    });
    }

     private void hitungText() {
        String text = jTextArea1.getText();

        // Hitung jumlah kata
        int wordCount = text.isEmpty() ? 0 : text.split("\\s+").length;

        // Hitung jumlah karakter
        int charCount = text.length();

        // Hitung jumlah kalimat menggunakan pemisah .!? untuk mengenali akhir kalimat
        int sentenceCount = text.isEmpty() ? 0 : text.split("[.!?]").length;

        // Hitung jumlah paragraf berdasarkan garis baru ganda sebagai pemisah
        int paragraphCount = text.isEmpty() ? 0 : text.split("\\n+").length;

        // Update JLabel dengan hasil perhitungan
        jLabel10.setText("" + wordCount);
        jLabel11.setText("" + charCount);
        jLabel12.setText("" + sentenceCount);
        jLabel13.setText("" + paragraphCount);
        
    }
~~~
• DocumentListener pada JTextArea untuk menghitung secara real-time
 ~~~
  
 ~~~
5. Variasi:
• Tambahkan fitur untuk menghitung jumlah kalimat dan paragraf
~~~
// Hitung jumlah kalimat menggunakan pemisah .!? untuk mengenali akhir kalimat
int sentenceCount = text.isEmpty() ? 0 : text.split("[.!?]").length;

// Hitung jumlah paragraf berdasarkan garis baru ganda sebagai pemisah
int paragraphCount = text.isEmpty() ? 0 : text.split("\\n+").length;

jLabel12.setText("" + sentenceCount);
jLabel13.setText("" + paragraphCount);
        
~~~
• Implementasikan fungsi pencarian kata tertentu dalam teks
~~~
private void jButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                         
       jButton2.addActionListener((ActionEvent e) -> {
            CariKata();
        });
    } 
 ~~~
• Sediakan opsi untuk menyimpan teks dan hasil perhitungan ke file
~~~
  if (userSelection == jFileChooser1.APPROVE_OPTION) {
        try (FileWriter writer = new FileWriter(fileChooser.getSelectedFile())) {
       
            writer.write("Teks:\n" + jTextArea1.getText() + "\n\n");
            writer.write("Jumlah Kata: " + jLabel10.getText() + "\n");
            writer.write("Jumlah Karakter: " + jLabel11.getText() + "\n");
            writer.write("Jumlah Kalimat: " + jLabel12.getText() + "\n");
            writer.write("Jumlah Paragraf: " + jLabel13.getText() + "\n");
            writer.write("Pencarian Kata '" + jTextField1.getText() + "': " + jLabel9.getText() + "\n");
            JOptionPane.showMessageDialog(this, "Hasil berhasil disimpan ke hasil_penghitungan.txt");
        } catch (IOException e) {
            JOptionPane.showMessageDialog(this, "Gagal menyimpan file: " + e.getMessage());
        }
        }
    }
~~~

## Hasil Setelah Di Run
![Cuplikan layar 2024-11-09 222128](https://github.com/user-attachments/assets/72a143e4-6420-460c-9116-ea29dc6f63d0)

## Indikator Penilaian:
| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    10    |
|  2  | Logika Program   |    20    |
|  3  | Kesesuaian UI    |    10    |
|  4  | Constructor      |    20    |
|  5  | Memenuhi Variasi |    40    |
|     | TOTAL        | 100 |


## Pembuat
Nama  : Muhammad Azhari Nur Pratama
NPM   : 2210010326
