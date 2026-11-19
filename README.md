# Post-its

Post-its coloridos, arrastáveis e redimensionáveis, com lembretes, visto de concluído e escrita à mão (caneta de tablet). As notas ficam guardadas no próprio aparelho.

Ficheiro principal: `index.html` (não tem dependências).

## Opção A: PWA no GitHub Pages (mais simples)

1. Cria um repositório no GitHub e carrega todos os ficheiros desta pasta.
2. Em **Settings > Pages**, escolhe **Deploy from a branch**, ramo `main`, pasta `/ (root)`.
3. Passado um minuto, a página fica em `https://O_TEU_UTILIZADOR.github.io/NOME_DO_REPOSITORIO/`.
4. No Chrome do tablet ou telemóvel, abre o endereço e escolhe **Instalar aplicação** (ou **Adicionar ao ecrã inicial**).

Fica com ícone próprio, abre em ecrã inteiro e funciona offline.
Limitação: os lembretes só disparam com a aplicação aberta.

## Opção B: APK Android (lembretes com a app fechada)

1. Carrega os mesmos ficheiros para o repositório (a pasta `.github` tem de ir também).
2. No GitHub, abre o separador **Actions**, escolhe **Gerar APK Android** e carrega em **Run workflow**.
3. Quando terminar (alguns minutos), descarrega o artefacto **postits-apk** e extrai o ficheiro `app-debug.apk`.
4. Copia o APK para o Android e instala (o telemóvel pede para permitir instalar de fontes desconhecidas).
5. Ao criar o primeiro lembrete, aceita a permissão de notificações.

Os lembretes são agendados no Android (notificações locais) e disparam mesmo com a app fechada.

Para mudares o identificador da app, edita `appId` em `capacitor.config.json` (por exemplo `pt.rogerio.postits`).

## Notas

- Alterar a aplicação: edita só o `index.html`. Se alterares ficheiros em cache (PWA), muda o nome `postits-v1` em `sw.js` para a versão nova ser apanhada.
- As notas não sincronizam entre aparelhos.
- O APK gerado é de depuração (debug), suficiente para uso pessoal. Publicar na Play Store exige assinar a app.
