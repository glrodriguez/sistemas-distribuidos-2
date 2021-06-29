# animeflix
Replica of Netflix but for anime

# Steps
Copy config.ini
Copy config.json

Backend
pip3 install -r requirements.txt
python3 main.py

Frontend
npm install
npm run start

Docker
docker run -exec -it -p 80:80 -p 5000:5000 -p 3000:3000 --name webserver 3eabd968c2ef
docker exec -it webserver /bin/bash
