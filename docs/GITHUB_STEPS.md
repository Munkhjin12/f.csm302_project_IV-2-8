# GitHub-д байрлуулах заавар (нэг repo, нэг удаа)

Зааварт: repository нь README.md, src/, tests/, docs/ бүтэцтэй, 9-р долоо хоногт Release/Tag нийтлэгдсэн,
багийн гишүүд хамтран ажилласан байх ёстой. Нууц түлхүүр, нууц үг оруулахгүй.

## 0. Хэрэв `src/c` дотор `git init` хийсэн бол (буруу, nested repo)
```sh
cd IV-2-8_scheduler
rm -rf src/c/.git
```

## 1. Repo-г хавтасны ЭХЭНД (IV-2-8_scheduler дотор) нэг удаа үүсгэх
```sh
cd IV-2-8_scheduler
git init
git branch -M main
git add .
git status          # fcfs, sjf, rr … executable файл ХАРАГДАХ ЁСГҮЙ (.gitignore хаасан)
git commit -m "Initial commit: IV-2-8 scheduler"
```
Хэрэв executable-ууд аль хэдийн commit хийгдсэн бол: `git rm --cached src/c/fcfs src/c/sjf src/c/priority src/c/rr src/c/priority_rr`

## 2. GitHub дээр хоосон repo үүсгээд холбох
GitHub → New repository (README, .gitignore, license НЭМЭХГҮЙ) → дараа нь:
```sh
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

## 3. Багаар хамтран ажиллах
- Settings → Collaborators-аас гишүүдийг нэмнэ.
- Гишүүн бүр өөрийн компьютер дээр нэг удаа: `git config --global user.name "Нэр"` ба `git config --global user.email "имэйл"`.
- Ажлын урсгал: `git pull` → өөрчлөлт хийх → `git add` → `git commit -m "тайлбар"` → `git push`.
  (эсвэл branch үүсгээд Pull Request нээнэ). Хуваарилсан ажлаа (README / Report Appendix A) өөр өөр commit-оор хийвэл
  GitHub-ийн ажиллагаа тайланд тусгагдана.

## 4. Release / Tag (9-р долоо хоног)
```sh
git tag -a v1.0 -m "БД1 хувилбар"
git push origin v1.0
```
GitHub → Releases → Draft a new release → tag v1.0 → IV-2-8_BD1_Report.pdf, IV-2-8_Manual.pdf хавсаргана.

## 5. Дараа нь
Report-ын Хавсралт C болон нүүр хуудсанд GitHub холбоос, Tag, commit-ын тоо, гишүүдийн ажлыг нөхнө.
