# DiziOdev

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DiziOdev
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Kaç öğrenci notu hesaplanacak?");
            byte kisi = byte.Parse(Console.ReadLine());
            double ortalama;
               

            string[,] ogrenciler = new string[kisi + 1, 6];
            ogrenciler[0, 0] = "Ad";
            ogrenciler[0, 1] = "Soyad";
            ogrenciler[0, 2] = "Vize";
            ogrenciler[0, 3] = "Final";
            ogrenciler[0, 4] = "Ortalama";
            ogrenciler[0, 5] = "HarfNotu";

           

            for (int i = 1; i < ogrenciler.GetLength(0); i++)
            {
                for (int j = 0; j < ogrenciler.GetLength(1); j++)
                {
                    switch (j)
                    {
                        case 0:
                            Console.WriteLine("Öğrenci Adı Giriniz: ");
                            ogrenciler[i, j] = Console.ReadLine();
                            break;
                        case 1:
                            Console.WriteLine("Öğrenci Soyadı Giriniz: ");
                            ogrenciler[i, j] = Console.ReadLine();
                            break;
                        case 2:
                            Console.WriteLine("Öğrenci Vize Notu Giriniz: ");
                            ogrenciler[i, j] = Console.ReadLine();
                            break;
                        case 3:
                            Console.WriteLine("Öğrenci Final Notu Giriniz: ");
                            ogrenciler[i, j] = Console.ReadLine();
                            break;
                        case 4:
                            ortalama = double.Parse(ogrenciler[i, 2]) * 0.4 + double.Parse(ogrenciler[i, 3]) * 0.6;
                            ortalama = Math.Round(ortalama, 2);
                            ogrenciler[i, 4] = Convert.ToString(ortalama);
                            break;
                        case 5:
                            ortalama = double.Parse(ogrenciler[i, 4]);
                            
                            if (ortalama >= 90 && ortalama <= 100)
                            {
                                ogrenciler[i, 5] = Convert.ToString("AA");
                            }
                            if (ortalama >= 80 && ortalama <= 89)
                            {
                                ogrenciler[i, 5] = Convert.ToString("BA");
                            }
                            if (ortalama >= 70 && ortalama <= 79)
                            {
                                ogrenciler[i, 5] = Convert.ToString("BB");
                            }
                            if (ortalama >= 60 && ortalama <= 69)
                            {
                                ogrenciler[i, 5] = Convert.ToString("CB");
                            }
                            if (ortalama >= 50 && ortalama <= 59)
                            {
                                ogrenciler[i, 5] = Convert.ToString("CC");
                            }
                            if (ortalama >= 0 && ortalama <= 49)
                            {
                                ogrenciler[i, 5] = Convert.ToString("FF");
                            }
                            break;
                        default:
                            break;
                    }
                    
                }
            }

            for (int i = 0; i < ogrenciler.GetLength(0); i++)
            {
                for (int j = 0; j < ogrenciler.GetLength(1); j++)
                {
                    Console.Write(ogrenciler[i,j] + "\t");
                }
                Console.WriteLine();
            }

           
           
           
            Console.ReadKey();
        }
        
    }
}
