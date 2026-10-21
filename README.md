# Casa Elétrica — projeto Capacitor (Android e iOS)

O app inteiro está em `www/index.html` (sem dependências externas).

## Testar no navegador do celular (mais rápido)
Coloque a pasta `www` em qualquer hospedagem estática (ou rode `npx serve www` no PC e abra o IP do PC no celular, na mesma rede).

## Gerar app nativo
Pré-requisitos: Node.js. Android: Android Studio. iOS: Mac com Xcode.

```bash
npm install @capacitor/core @capacitor/cli
npm install @capacitor/android @capacitor/ios
npx cap add android      # e/ou: npx cap add ios
npx cap sync
npx cap open android     # abre no Android Studio -> Run
npx cap open ios         # abre no Xcode -> Run
```

Depois de editar `www/index.html`, rode `npx cap sync` de novo.
O projeto fica salvo no armazenamento do app (localStorage), e o botão 💾 exporta/importa um texto de backup.
Ícone e splash: use `npx @capacitor/assets generate` com uma imagem em `assets/icon.png`.

## Gerar o APK SEM Android Studio (na nuvem, grátis)
1. Crie uma conta em github.com e um repositório novo (ex.: `casa-eletrica`).
2. Envie todo o conteúdo desta pasta (inclusive `.github/workflows/build-apk.yml`). Pelo site: Add file > Upload files. Se o celular não enviar a pasta oculta `.github`, use Add file > Create new file, digite o nome `.github/workflows/build-apk.yml` e cole o conteúdo do arquivo.
3. Abra a aba **Actions** > **Build APK** > **Run workflow**. Leva uns 5 a 10 minutos.
4. Ao terminar, abra a execução e baixe o artefato **casa-eletrica-apk** (um .zip com o `app-debug.apk`).
5. No celular, extraia o zip, abra o APK e permita "instalar de fontes desconhecidas".
