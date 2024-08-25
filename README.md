# tas_kagit_makas
Aygaz Python Bootcamp Projesi
## Projenin kodlarına [buraya tıklayarak](https://colab.research.google.com/drive/1I8MRhItL3AbWe-_ssjyQnTmYhRcKVMhL#scrollTo=xsXAhcV25R1S) ulaşabilirsiniz.
```
pip install tabulate
# Bu kütüphane sonuçları tablo halinde yazdırmak için.
```
```
import random
from tabulate import tabulate

def get_computer_choice():
    """Bilgisayarın rastgele bir seçim yapmasını sağlar."""
    choices = ['taş', 'kağıt', 'makas']
    return random.choice(choices) #Random seçim.

def get_user_choice():
    """Kullanıcının geçerli bir seçim yapmasını sağlar."""
    choice = input("Taş, Kağıt veya Makas seçin: ").lower() # Kullanıcının girdiği seçimi küçük harfe çeviriyoruz. Böylece büyük/küçük harf farkı olmaz.
    while choice not in ['taş', 'kağıt', 'makas']:
        print("Geçersiz seçim. Lütfen Taş, Kağıt veya Makas girin.") #Geçersiz bir seçim yaparsa, doğru bir seçim yapana kadar kullanıcıya tekrar sorulur.
        choice = input("Taş, Kağıt veya Makas seçin: ").lower()
    return choice

def determine_winner(user_choice, computer_choice):
    """Kullanıcının ve bilgisayarın seçimlerini karşılaştırarak oyunun sonucunu belirler."""
    if user_choice == computer_choice:
        return "Beraberlik"
    elif (user_choice == 'taş' and computer_choice == 'makas') or \
         (user_choice == 'kağıt' and computer_choice == 'taş') or \
         (user_choice == 'makas' and computer_choice == 'kağıt'): #Taş makası yener, kağıt taşı yener, makas kağıdı yener. Bu kuralları kullanarak sonucu belirleriz.
        return "Kullanıcı kazandı"
    else:
        return "Bilgisayar kazandı"

def play_single_game(round_number):
    """Tek bir oyunu oynar ve sonucu döndürür."""
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()
    
    print(f"Bilgisayarın seçimi: {computer_choice.capitalize()}")
    
    result = determine_winner(user_choice, computer_choice)
    print(result)
    return round_number, user_choice, computer_choice, result

def play_game():
    """Oyunu birden fazla tur oynar ve genel sonuçları tablo şeklinde gösterir."""
    print("Taş-Kağıt-Makas oyununa hoş geldiniz!")
    
    rounds = int(input("Kaç tur oynamak istersiniz? "))
    
    game_results = []
    user_score = 0
    computer_score = 0
    
    for i in range(rounds):
        print(f"\nTur {i+1}:")
        round_number, user_choice, computer_choice, result = play_single_game(i + 1)
        
        if result == "Kullanıcı kazandı":
            user_score += 1
        elif result == "Bilgisayar kazandı":
            computer_score += 1
        
        # Oyun sonuçlarını toplama
        game_results.append([round_number, user_choice, computer_choice, result])
    
    print("\nOyun Bitti!")
    
    # Skorları ve oyun sonuçlarını tablo halinde yazdırma
    print(f"\nKullanıcı Skoru: {user_score}")
    print(f"Bilgisayar Skoru: {computer_score}")
    
    if user_score > computer_score:
        print("Tebrikler, oyunu kazandınız!")
    elif user_score < computer_score:
        print("Bilgisayar kazandı. Daha şanslı bir sonraki oyunda!")
    else:
        print("Beraberlik! Yine de iyi oynadınız.")
    
    # Sonuçları tablo olarak yazdırma
    headers = ["Tur", "Kullanıcı Seçimi", "Bilgisayar Seçimi", "Sonuç"]
    print("\nOyun Sonuçları:")
    print(tabulate(game_results, headers=headers, tablefmt="grid"))

if __name__ == "__main__":
    play_game()


```
