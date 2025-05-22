# Discord Image Classification Bot 🤖🖼️

Bu proje, bir Discord sunucusunda çalışarak resim sınıflandırma işlemi yapan basit bir bottur. Kullanıcılar resim gönderdiğinde, bot bu resmi indirir ve bir makine öğrenmesi modeli ile sınıflandırır.

## Özellikler

- `$hello`: Botun çalıştığını doğrular.
- `$heh [sayı]`: Belirtilen sayıda `"he"` ifadesini tekrarlar (varsayılan: 5).
- `$check`: Kullanıcının gönderdiği resmi sınıflandırır.

## Gereksinimler

- Python 3.7+
- Aşağıdaki Python paketleri:
  - `discord.py`
  - `tensorflow` (veya `keras`, modelinize bağlı olarak)
  - Projenize özel `model.py` dosyası (`get_class` fonksiyonunu içermeli)

## Kurulum

1. Depoyu klonlayın:
    ```bash
    git clone https://github.com/kullanici-adi/discord-image-classification-bot.git
    cd discord-image-classification-bot
    ```

2. Sanal ortam oluşturun ve bağımlılıkları yükleyin:
    ```bash
    python -m venv venv
    source venv/bin/activate  # Windows için: venv\Scripts\activate
    pip install -r requirements.txt
    ```

3. Gerekli dosyaları yerleştirin:
    - `keras_model.h5`: Eğittiğiniz makine öğrenmesi modeli
    - `labels.txt`: Modelin sınıf etiketleri
    - `model.py`: `get_class` fonksiyonunu içermeli. Örnek:
      ```python
      def get_class(model_path, labels_path, image_path):
          # Model yükleme ve tahmin işlemi
          return "Tahmin edilen sınıf"
      ```

4. `.env` dosyası oluşturun veya `bot.run("TOKEN")` satırında `"TOKEN"` yerine kendi Discord bot tokenınızı girin.

## Kullanım

Botu başlatmak için:

```bash
python bot.py
