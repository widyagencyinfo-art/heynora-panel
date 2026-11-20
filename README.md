# panel.heynora · panel interno de Hey Nora (20-nov-2026)

Panel de cristal («glass») con todo lo de Hey Nora: clientes (Motovatio…), 🔥 por contestar, llamadas,
qué mensaje y qué cumplido funcionan, y el tracker del frío del 642.

- **Una sola página** (`index.html`), publicada con **GitHub Pages** (repo `widyagencyinfo-art/heynora-panel`), de momento en https://widyagencyinfo-art.github.io/heynora-panel/ (para `panel.heynora.es`: CNAME en Cloudflare y dominio en Settings → Pages).
- **Entrar:** con el usuario de panel.widy.agency (Supabase Auth). La página solo lleva la clave pública «anon»;
  los datos los protege el RLS del panel. Nada secreto en el repo.
- **Datos:** `leads` y `meetings` del panel (organización Widy, concesionarios/642) + almacén privado `heynora-panel`:
  `tracker.json` (lo sube el vigía del Mac mini cada noche a las 00:00, `seguimiento.py --subir`) y `clientes.json` (se edita desde el panel).
  Reglas del almacén: solo las dos cuentas de Darío leen y guardan (políticas «heynora panel …» en `storage.objects`).
- **Probar en local:** `cd ~/heynora/panel && python3 -m http.server 4317` → http://localhost:4317
- **Publicar cambios:** `git add -A && git commit -m "…" && git push` (Pages se actualiza solo en ~1 min).
