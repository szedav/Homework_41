# GitHub-Homework - DevOps Feladat

Ez a repository egy alapvető CI/CD (Continuous Integration / Continuous Deployment) folyamatot mutat be GitHub Actions segítségével.

## A repository tartalma

* **Dockerfile**: Meghatározza az egyedi Nginx alapú image felépítését.
* **index.html**: A weboldal tartalma, amely megjeleníti a "DevOps homework by: <NEVED>" feliratot.
* **.github/workflows/docker-publish.yml**: Az automatizációs szkript, ami minden `main` branch-re történő feltöltéskor (push) lefut.

## Működési elv
A GitHub Action automatikusan:
1. Figyeli a `main` ágat.
2. Push esetén bejelentkezik a Docker Hub-ra (titkosított hitelesítő adatokkal).
3. Lefuttatja a Docker build folyamatot a Dockerfile alapján.
4. Feltölti az elkészült image-et a megadott Docker Hub fiókba `homework:latest` néven.

## Biztonság
A hitelesítéshez szükséges adatokat (felhasználónév, token) **GitHub Secrets** tárolja, így azok soha nem kerülnek bele a forráskódba vagy a logokba.