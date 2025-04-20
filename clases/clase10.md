# Material para la clase 10

Este es el código que debes agregar para tu nueva Github Action

```yml
name: API Contactos CD/CD

on:
  push:
    branches: [ "main" ]

env:
  IMAGE_BASE_NAME: aminespinoza/apicontactos:latest

jobs:
  API_Image:
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: src
    steps:
      - name: Check out the repo
        uses: actions/checkout@v3
      - name: Build Docker NET image
        run: | 
          docker build --platform linux --tag $IMAGE_BASE_NAME -f .
```
