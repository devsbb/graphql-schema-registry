## Examples

## Federated gateway + schema registry + 2 services

![](https://app.lucidchart.com/publicSegments/view/d7d424de-e45a-4a0f-902d-e9030d06b07f/image.png)

### How to run

- Start graphql-schema-registry. Wait until DB & UI work at http://localhost:6001/

```
nvm use
npm install
npm run build
docker-compose up
```

- Start gateway_service (not dockerized)

```
cd gateway_service && npm install && node index.js
```

- (In separate terminals) Start federated services

```
cd federated_service_a && npm install && node index.js
cd federated_service_b && npm install && node index.js
```

- Check graphql-schema-registry UI. It should contain now schema from both services
  http://localhost:6001/

- Open gateway's playground UI in the browser and try to make request to both services
  http://localhost:6100
  <img width="681" alt="Screenshot 2020-09-01 at 23 46 09" src="https://user-images.githubusercontent.com/445122/91904286-5a7f2200-ecad-11ea-9d63-43a96f96e886.png">
