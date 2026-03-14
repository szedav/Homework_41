# GitHub-Homework

A házi feladat során egy automatizált CI/CD folyamatot kellett létrehozni Github Actions segítségével

## Repository tartalma 

- **Dockerfile**: Meghatározza az egyedi Nginx alapú image felépítését.
- **index.html**: A weboldal tartalma, amely megjeleníti a "DevOps homework by: <Szecsi David>" feliratot.
- **.github/workflows/docker-publish.yml**: Az automatizációs szkript, ami minden `main` branch-re történő feltöltéskor (push) lefut.

## CI/CD munkafolyamat
1. **Push**: A kód feltöltése a `main` ágra.
2. **Build**: A Dockerfile alapú image építése.
3. **Push**: Az elkészült image feltöltése a Docker Hub-ra.


## Biztonság
A hitelesítéshez szükséges adatokat (felhasználónév, token) **GitHub Secrets** tárolja, így azok soha nem kerülnek bele a forráskódba vagy a logokba.
