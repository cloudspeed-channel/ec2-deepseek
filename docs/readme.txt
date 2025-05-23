
- Copy files to ec2 instance -
scp -i "./deepseek.pem" C:\Users\HP\Documents\digitalspeed\deepseek-project\* ec2-user@NEW-EC2-IP-ADDRESS:/home/ec2-user/

- Connect to your EC2 instance -
ssh -i "./key/deepseek.pem" ec2-user@IP-ADDRESS

- Start the files accordingly -
docker-compose -f docker-compose-ol.yml up -d --build
docker-compose -f docker-compose-traefik.yml up -d --build

- Confirm all containers are running -
docker ps

- Test your API
curl -X GET "https://superearner.online/"

curl -X POST "https://superearner.online/generate" -H "Content-Type: application/json" -d "{\"prompt\": \"say hi\", \"model\": \"deepseek-r1:7b\", \"stream\": false, \"max_tokens\": 300, \"temperature\": 0.4}"

- Start your streamlit app -
streamlit run app.py

- Query your app -
hey
---