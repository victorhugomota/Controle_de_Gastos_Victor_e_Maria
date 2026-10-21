# Controle Financeiro — Victor & Maria

Site de controle financeiro da família (salários, cartões, boletos, mercado, estimativas e reservas).
Publicado pelo GitHub Pages: https://victorhugomota.github.io/Controle_de_Gastos_Victor_e_Maria/

## Como funciona

- Todo o app está em `index.html` (HTML + CSS + JavaScript, bibliotecas via CDN). Não precisa de build.
- Os dados ficam no Firebase Firestore (projeto `comprasmercado-23913`), coleções:
  `compras`, `entradas`, `faturas`, `boletos`, `reservas`, `estimativas`.
- Acesso com login Google. Quem pode ler/gravar é definido em [`firestore.rules`](firestore.rules).
- Exclusões vão para a **Lixeira** (campo `excluidoEm`) e podem ser restauradas. As regras bloqueiam exclusão definitiva.
- Backup: botão **"Exportar Backup (JSON)"** na Visão Geral.
- App instalável no celular (`manifest.json`, `sw.js`, `icons/`).

## Configuração do Firebase (feita uma vez, no console)

1. **Authentication → Get started → Sign-in method → Google → Ativar.**
2. **Authentication → Settings → Authorized domains → Add domain:** `victorhugomota.github.io`
3. **Firestore Database → Regras:** colar o conteúdo de `firestore.rules`, trocar os 2 e-mails e publicar.

## Testar localmente

```bash
python -m http.server 5173
```

Abrir http://localhost:5173 (o login funciona em `localhost`).
