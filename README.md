# portfolio

> `ssh -p 2222 40.233.78.82`

terminal portfolio — built with ssh2 + typescript.
navigate with arrow keys, press q to quit.

## tabs

- **home** — bio and contact
- **creations** — github projects
- **reflections** — essays and writing

## stack

- `ssh2` — ssh server
- `tsx` — typescript runner
- `node.js` — runtime
- braille ascii portrait generated with pillow

## run locally
```bash
git clone https://github.com/bluestriker03/personal_website
cd personal_website
npm install
ssh-keygen -t ed25519 -f ./host_key -N ""
sudo tsx server.tsx
```

then connect:
```bash
ssh localhost -p 2222
```

## deploy

hosted on **oracle cloud free tier** running **ubuntu 22.04**.
kept alive with pm2.
domain via is-a.dev (coming soon).

## server setup
```bash
# on ubuntu server
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo bash -
sudo apt install -y nodejs
sudo npm install -g tsx pm2
pm2 start "sudo tsx server.tsx" --name portfolio
pm2 save && pm2 startup
```
