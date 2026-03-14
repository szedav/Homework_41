# GitHub-Homework

A házi feladat során egy automatizált CI/CD folyamatot kellett létrehozni Github Actions segítségével

## Repository tartalma 

- **Docker**: Meghatározza az egyedi Nginx alapú image felépítését.
- **index.html**: A weboldal tartalma, amely megjeleníti a "DevOps homework by: <Szecsi David>" feliratot.
- **.github/workflows/docker-publish.yml**: Az automatizációs szkript, ami minden `main` branch-re történő feltöltéskor (push) lefut.

## Működési leírás
1. A GitHub Actions minden push esetén lefut.
2. A `docker-publish.yml` fájlban definiált lépések szerint bejelentkezik a Docker Hub-ra (titkosított `Secrets` használatával).
3. Felépíti a `Docker` alapján az image-et.
4. Publikálja a kész image-et a `szedav/homework:latest` címre.

## Hogyan futtasd lokálisan?
Ha telepítve van a Docker a gépeden, az alábbi paranccsal ellenőrizheted a munkát:

```bash
docker run -d -p 8080:80 szedav/homework:latest
Ezután nyisd meg a http://localhost:8080 címet a böngésződben.
Ha minden jól sikerült akkor az alábbi kiírás fogad:
"DevOps homework by: <Szecsi David>"

