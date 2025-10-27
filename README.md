# Velocímetro AbilioShow

Este é o projeto completo para o aplicativo Android "Velocímetro AbilioShow", que exibe a velocidade atual em km/h utilizando o GPS do dispositivo. O projeto foi configurado para ser aberto diretamente no **Android Studio**.

## Estrutura do Projeto

O projeto segue a estrutura padrão de um aplicativo Android em Kotlin:

- `settings.gradle`: Configuração do projeto Gradle.
- `build.gradle`: Configuração global do Gradle.
- `app/build.gradle`: Configuração do módulo do aplicativo, incluindo as dependências para o serviço de localização (`play-services-location`).
- `app/src/main/AndroidManifest.xml`: Declara as permissões de localização (`ACCESS_FINE_LOCATION` e `ACCESS_COARSE_LOCATION`) necessárias para o GPS.
- `app/src/main/java/com/abilioshow/velocimetro/MainActivity.kt`: Contém a lógica principal em Kotlin:
    - Solicita permissões de localização ao usuário.
    - Utiliza `FusedLocationProviderClient` para obter atualizações de localização.
    - Converte a velocidade de `m/s` (metros por segundo) para `km/h` (quilômetros por hora) e atualiza a interface.
- `app/src/main/res/layout/activity_main.xml`: Define o layout da tela, com um `TextView` grande para exibir a velocidade.
- `app/src/main/res/values/strings.xml`: Contém as strings de texto, incluindo o nome do app e textos de status.

## Como Abrir e Emular no Android Studio

1.  **Abrir o Projeto:**
    - Abra o **Android Studio**.
    - Selecione **"Open"** (Abrir) e navegue até a pasta `VelocimetroAbilioShow`.
    - O Android Studio irá sincronizar o projeto e baixar as dependências do Gradle.

2.  **Emular o Aplicativo (Simulação de Velocidade):**
    - Crie ou selecione um **Android Virtual Device (AVD)** no AVD Manager.
    - Execute o aplicativo no AVD.
    - **Para testar a função de velocímetro, você precisará simular o movimento do GPS no emulador.**
    - No emulador, clique no ícone de três pontos (`...`) para abrir os **"Extended Controls"** (Controles Estendidos).
    - Vá para a aba **"Location"** (Localização).
    - Você pode usar a função **"Route"** (Rota) para simular um movimento com velocidade definida ou enviar coordenadas manualmente. O emulador irá simular a velocidade de deslocamento para o aplicativo.

## Como Gerar o Arquivo APK

Existem duas formas principais de gerar o APK:

### 1. APK de Debug (Para Testes)

O APK de debug é usado para testes rápidos e não é adequado para publicação na Google Play Store.

1.  No Android Studio, vá em **"Build"** (Construir) na barra de menu.
2.  Selecione **"Build Bundle(s) / APK(s)"** (Construir Bundle(s) / APK(s)).
3.  Clique em **"Build APK(s)"** (Construir APK(s)).
4.  Após a conclusão, uma notificação aparecerá com um link **"Locate"** (Localizar). O APK estará em `VelocimetroAbilioShow/app/build/outputs/apk/debug/app-debug.apk`.

### 2. APK/AAB de Release (Para Publicação)

Para gerar um arquivo de release (APK ou o formato mais recente e recomendado, AAB - Android App Bundle) assinado, que pode ser enviado para a Google Play Store:

1.  No Android Studio, vá em **"Build"** (Construir).
2.  Selecione **"Generate Signed Bundle / APK..."** (Gerar Bundle / APK Assinado...).
3.  Escolha **"Android App Bundle"** (recomendado) ou **"APK"**.
4.  Clique em **"Next"** (Próximo).
5.  **Crie uma Key Store:**
    - Clique em **"Create new..."** (Criar novo...).
    - Preencha os detalhes da sua Key Store (caminho, senha, alias, senhas de chave, etc.). **Guarde esta Key Store e as senhas em segurança!**
6.  Selecione o módulo `app`.
7.  Escolha o tipo de build **`release`**.
8.  Clique em **"Finish"** (Finalizar).
9.  O arquivo de release (`.aab` ou `.apk`) será gerado no diretório `app/release/`.

---
**Observação:** O aplicativo foi desenvolvido para usar o **Binding de Visualização (`View Binding`)**, o que torna o código mais seguro e limpo. A dependência e a configuração para isso foram incluídas no `app/build.gradle`.

