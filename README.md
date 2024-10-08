# Taş-Kağıt-Makas Oyunu

Bu Python uygulaması, klasik Taş-Kağıt-Makas oyununu terminal üzerinde bilgisayara karşı oynayabileceğiniz bir interaktif oyun sunar. Oyun, kullanıcı ile bilgisayar arasında birden fazla tur oynanabilir ve sonuçlar her tur sonunda tablo halinde görüntülenir.

## Proje Hakkında
Taş-Kağıt-Makas oyunu, kullanıcıların seçimlerine göre kazananın belirlendiği basit bir oyun algoritması üzerine kuruludur. Proje, Python'daki *random* modülünü kullanarak bilgisayarın rastgele bir seçim yapmasını sağlar ve *tabulate* kütüphanesi ile oyun sonuçları görsel olarak daha anlaşılır bir şekilde sunulur.

Bu proje, Python programlama bilgilerini geliştirmek ve terminalde basit bir oyun deneyimi sunmak amacıyla geliştirilmiştir.

## Özellikler

- **Rastgele Bilgisayar Seçimi**: Bilgisayar her turda taş, kağıt veya makas seçeneklerinden birini rastgele seçer.
- **Kullanıcı Girdisi**: Kullanıcı geçerli bir seçim yapmak zorundadır. Geçersiz bir seçim yaparsa, tekrar denemesi istenir.
- **Kazananı Belirleme**: Oyun kurallarına göre her turun kazananı belirlenir.
- **Çoklu Tur Desteği**: Kullanıcı belirlediği sayıda tur oynayabilir.
- **Tablo Formatında Sonuçlar**: Her turdan sonra ve oyun sonunda sonuçlar tablo halinde kullanıcıya sunulur.

## Kullanım

Oyunu çalıştırdığınızda, size kaç tur oynamak istediğiniz sorulacak. Ardından, her turda Taş, Kağıt veya Makas seçeneklerinden birini girerek bilgisayarla karşılaşacaksınız. Oyun her turdan sonra sonucu ve sonunda genel skoru tablo formatında görüntüler.

## 
Kod Yapısı
Projenin ana dosyası main.py olup, şu temel işlevleri içerir:

- **get_computer_choice()**: Bilgisayarın taş, kağıt veya makas seçimi yapmasını sağlar.
- **get_user_choice()**: Kullanıcının geçerli bir seçim yapmasını sağlar.
- **determine_winner()**: Kullanıcı ve bilgisayarın seçimlerine göre kazananı belirler.
- **play_single_game()**: Tek bir turu oynatır ve sonucu döndürür.
- **play_game()**: Birden fazla tur oynatır ve sonuçları tablo halinde gösterir.

## Testler

Proje basit ve terminal tabanlı olduğundan, test etmek için oyunu birkaç kez çalıştırıp farklı seçimlerle sonuçları gözlemleyebilirsiniz.
