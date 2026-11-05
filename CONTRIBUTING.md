# MUMTAZ — Katkıda Bulunma

MUMTAZ (`GNU GPL-3.0-or-later`) açık kaynaklı bir kültür kütüphanesidir. Her türlü katkı (kod, belge, test, çeviri) kabul edilir.

## 🛠️ Geliştirme

- **Rust 1.92+** gereklidir.
- **Build**: `cargo build --release -p mumtaz-desktop`
- **Run**: `cargo run --release -p mumtaz-desktop`
- **Test**: `cargo test --workspace` (eğer test paketi tanımlıysa)
- **Dil**: Commit mesajları **konvenyonal commit** formatında olsun:
  ```
  feat: Yeni bir özellik
  fix: Bir hata düzeltmesi
  docs: Dokümantasyon güncellemesi
  chore: Bakım/Paket güncellemesi
  ```
- **New feature**: `docs/ROADMAP.md` çizelgesindeki ilgili maddeyi tamamlayın, ardından ilgili issue'ı kapatın.

## 📨 Issue ve Pull Request

1. **Önce issue açın** — sorunun ya da özelliği açık bir başlıkla; **etiket** olarak `good first issue` ya da `help wanted` belirtebilirsiniz.
2. **Fork** oluşturun ve kendi dalınıza (`type/short-desc`) geçin (örnek: `feat/hamberg-menu`).
3. **Commit'ler** convenciyon şeklinde olsun, body'de gerekirse `Co-Authored-By` eklemeyin.
4. **PR** açın, `Closes #issue-number` ifadesiyle; Acıklamalar (`Reviewers`) isterseniz `@MAKHMUDuz`'i etiketleyebilirsiniz.

## 📄 Lisans

Katkılarınız `GNU GPL-3.0-or-later` lisansı kapsamına girer; lütfen `LICENSE` dosyasını inceleyin.

Teşekkürler! 🌟
