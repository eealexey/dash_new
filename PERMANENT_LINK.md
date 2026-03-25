# Permanent link to the dashboard

To get a **stable, shareable URL** for the Nexus DC dashboard (instead of `localhost`), use one of these options.

---

## GitHub Pages — пошагово (на русском)

### Шаг 1: Репозиторий на GitHub

1. Зайди на [github.com](https://github.com), войди в аккаунт.
2. Нажми **New repository** (или **+** → New repository).
3. Укажи имя, например: `nexus-dashboard`.
4. Выбери **Public**, галочку **Add a README** можно не ставить.
5. Нажми **Create repository**.

### Шаг 2: Отправить код на GitHub

Репозиторий и коммит уже готовы. В терминале (из папки проекта) выполни:

```bash
cd /home/cursor/datacenter-platform-dashboard
git push -u origin main
```

Логин: **eealexey**. Если запросит пароль — введи **Personal Access Token** (GitHub → Settings → Developer settings → Personal access tokens), а не обычный пароль.

### Шаг 3: Включить GitHub Pages

1. На странице репозитория открой **Settings** (Настройки).
2. Слева выбери **Pages** (в блоке "Code and automation").
3. В **Build and deployment**:
   - **Source**: Deploy from a branch  
   - **Branch**: `main`, папка **/ (root)**  
   - Нажми **Save**.

### Шаг 4: Открыть дашборд

Через 1–2 минуты сайт будет доступен по адресу:

**`https://eealexey.github.io/nexus-dashboard/`**

Эту ссылку можно сохранять и передавать — она постоянная.

---

## 1. GitHub Pages (English)

1. Create a GitHub repository and push this folder:
   ```bash
   cd /home/cursor/datacenter-platform-dashboard
   git init
   git add index.html README.md DASHBOARD_GUIDE.md PERMANENT_LINK.md
   git commit -m "Nexus DC dashboard"
   git remote add origin https://github.com/YOUR_USERNAME/datacenter-dashboard.git
   git push -u origin main
   ```

2. On GitHub: **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main`, folder: **/ (root)** → Save.

3. Your dashboard will be available at:
   **`https://YOUR_USERNAME.github.io/datacenter-dashboard/`**

(Replace `datacenter-dashboard` with your repo name if different.)

---

## 2. Netlify (free, drag & drop)

1. Go to [netlify.com](https://www.netlify.com) and sign up (free).
2. Drag the folder **datacenter-platform-dashboard** (or just `index.html`) into the Netlify drop zone.
3. Netlify will give you a URL like **`https://random-name-12345.netlify.app`**.
4. You can set a custom subdomain in Site settings (e.g. `nexus-dc-demo.netlify.app`).

---

## 3. Vercel (free)

1. Install Vercel CLI: `npm i -g vercel`
2. From the project folder:
   ```bash
   cd /home/cursor/datacenter-platform-dashboard
   vercel
   ```
3. Follow the prompts. You'll get a URL like **`https://datacenter-platform-dashboard-xxx.vercel.app`**.

Or connect the GitHub repo in the [Vercel dashboard](https://vercel.com) for automatic deploys on every push.

---

## 4. Cursor Ports (while developing)

If you run the dashboard with `python3 -m http.server 8080` inside Cursor:

1. Open the **Ports** panel (View → Ports or the ports tab).
2. Find port **8080** and click **Open in Browser** (or the globe icon).
3. Cursor will give you a **forwarded URL** (e.g. `https://8080-xxx.preview.cursor.com`). This link is stable for your current dev session and can be shared with others as long as the server and Cursor are running.

This is useful for quick sharing during development; for a truly permanent link, use GitHub Pages, Netlify, or Vercel.

---

## Summary

| Method           | Permanent? | Best for                    |
|------------------|------------|-----------------------------|
| **GitHub Pages** | Yes        | Public repo, simple deploy  |
| **Netlify**      | Yes        | No git needed, custom domain|
| **Vercel**       | Yes        | Git-based, auto deploy      |
| **Cursor Ports** | Session    | Quick share while coding    |

For a **permanent** link, prefer **GitHub Pages** or **Netlify**.
