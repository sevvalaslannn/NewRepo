# NewRepo
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;

namespace Kitaplık
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int toplamfiyat = 0;
            string secim;
            Console.WriteLine("*************************************************************************");
            Console.WriteLine();
            Console.WriteLine(" Türkçe Kitaplar                 **          Yabancı  Kitaplar");
            Console.WriteLine();
            Console.WriteLine("  1-ÇalıKuşu:Reşat Nuri          **  5-Tuna  Kılavuzu:Jules Verne");
            Console.WriteLine();
            Console.WriteLine("  2-Yaban:Yakup Kadri            **  6-Bir Kuzey Macerası:Jack London");
            Console.WriteLine();
            Console.WriteLine("  3-Sinekli Bakkal:Halide Edip   **  7-Altıncı Koğuş:Anton Çehov");
            Console.WriteLine();
            Console.WriteLine("  4-Tehlikeli Oyunlar:O.Atay     **  8-Kumarbaz:Dostoyevski");
            Console.WriteLine();
            Console.WriteLine("**************************************************************************");
            Console.WriteLine();
            Console.WriteLine("***** Islemler Menusu *****");
            Console.WriteLine();
            Console.WriteLine("1-Fiyat Sorgulama");
            Console.WriteLine("2-Yeni Okur Kaydı");
            Console.WriteLine("3-Günün Kitabi");
            Console.WriteLine("4-Kitap Arşivi");
            Console.WriteLine("5-Yeni Kitap Satın Al");
            Console.WriteLine("6-Oyun");
            Console.WriteLine();
            Console.WriteLine("İşlem yapmak istedigin numara nedir? ");
            char islem;
            islem = Convert.ToChar(Console.ReadLine());
            if (islem == '1')
            {
                Console.WriteLine();
                Console.Write("Lütfen fiyatını ogrenmek istedin kitabın numarasını girin: ");
                string numara;
                numara = Console.ReadLine();
                switch (numara)
                {
                    case "1": Console.Write("ÇalıKuşu kitabi 20 Tl"); break;
                    case "2": Console.Write("Yaban kitabi 10 Tl"); break;
                    case "3": Console.Write("Sinekli Bakkal kitabi 18 Tl"); break;
                    case "4": Console.Write("Tehlikeli Oyunlar kitabi 15 Tl"); break;
                    case "5": Console.Write("Tuna  Kılavuzu kitabi 12 Tl"); break;
                    case "6": Console.Write("Bir Kuzey Macerası kitabi 10 Tl"); break;
                    case "7": Console.Write("Altıncı Koğuş kitabi 19 Tl"); break;
                    case "8": Console.Write("Kumarbaz kitabi 25 Tl"); break;


                }
            }
                if (islem == '2')
                {
                   
                   
                    Console.WriteLine("******** Yeni Okur Kaydı **********");
                    
                    String isim,soyisim,üniversite;
                    Console.Write("isminizi giriniz: ");
                    isim = Console.ReadLine();
                    Console.Write("soyisminizi giriniz: ");
                    soyisim = Console.ReadLine();
                    Console.Write("üniversitenizin ismini giriniz: ");
                    üniversite = Console.ReadLine();

                    string dosya = "C://Users//Monster//OneDrive//Desktop//Okur.txt";
                     StreamWriter sw = new StreamWriter(dosya);
                sw.WriteLine(isim);
                sw.WriteLine(soyisim);
                sw.WriteLine(üniversite);
                sw.Close();



                }
                if (islem == '3')
                {
                    Console.WriteLine("**************************************");
                    Console.WriteLine();
                    Console.WriteLine("******* Bugünün Kitabı:Çalıkuşu ******");
                     Console.WriteLine();
                Console.WriteLine("**************************************");
            }
                if (islem == '4')
                {
                Console.WriteLine();
                Console.WriteLine("**************************************");
                Console.WriteLine();
                FileStream fs = new FileStream ("C://Users//Monster//OneDrive//Desktop//kitaplar.txt" ,FileMode.Open, FileAccess.Read); 
                StreamReader st=new StreamReader(fs);
                string metin=st.ReadLine();
                while (metin != null)
                {
                    Console.WriteLine(metin);
                    metin = st.ReadLine();
                }
                st.Close();
                fs.Close();
                Console.WriteLine();
                Console.WriteLine("**************************************");
            }
        
                if (islem == '5')
                {
                    for(int i = 0; i <100;i++)
                {
                    Console.WriteLine();
                    Console.Write("Alacagınız kitabın numarası: ");
                    secim = Console.ReadLine();
                    if( secim == "1")
                    {
                        toplamfiyat = toplamfiyat + 20;
                    }
                    else if ( secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 10;
                    }
                    else if (secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 18;
                    }
                    else if (secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 15;
                    }
                    else if (secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 12;
                    }
                    else if (secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 10;
                    }
                    else if (secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 19;
                    }
                    else if (secim == "2")
                    {
                        toplamfiyat = toplamfiyat + 25;
                    }else
                    {
                        Console.WriteLine("böyle bir kitap numarası yok");
                        Console.WriteLine();
                        Console.Write("Başka bir kitap almak ister misin ?");
                        string cevap;
                        cevap= Console.ReadLine();
                        if (cevap == "h" || cevap == "H" || cevap == "hayır" || cevap == "HAYIR") 
                            break;
                    }
                    Console.WriteLine("Toplam Tutar: " + toplamfiyat);

                }
                }
                if (islem == '6')
                {
                    Console.WriteLine();
                    Console.WriteLine("islem:Oyun");
                }

                Console.ReadKey();

            }
        }
    }

