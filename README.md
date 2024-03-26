### Repairify Workshop

This is part 3 of the Repairify blog workshop hosted by UTDesign Makerspace

---

```bash
docker build -t gatsby-blog .
docker run -d --name blog-server -p 80:80 gatsby-blog
```

```bash
docker build -f Dockerfile.test -t blog-test .
docker run -d --name tests blog-test
```

```bash
docker-compose up
docker-compose up -d # detached mode
docker-compose up --build
docker-compose down
```

```bash
fly launch
fly apps destroy repairify-blog-part3
```