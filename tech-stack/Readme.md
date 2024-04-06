# Tech stack

## Front-end
1. Build tool: Vite. Preferred over Next and CRA for its better developer experience.
2. Routing: React router. Chosen for familiarity and ease of use.
3. State management: Zustand. Preferred over Redux and others for simple API, use without hooks which pairs well for data loading using react-router and for its subscribe api which allows us to listen for updates to state without rerendering the component.
4. Animation library: Framer-motion. Chosen for versatility and simple api.
5. 3D graphics and Physics: Threejs through react-three-fiber and Rapier
6. Styling solution: Tailwind + postcss. Chosen for ease-of-use and customisability. 

## Back-end
1. Middleware and routing: Expressjs. Chosen for simplicity and faster development.
2. Authentication: Passportjs.
3. Bidirectional socket communication: Socket.io.
4. Database querying: Mongoose.
5. Managing content: Contentful.

## SSR
1. AWS Lambda - caches to Redis and serves the cached response
2. Puppeteer - Gets content from main server when cached response is not available.
3. Pulumi - Manages the provisioning of AWS resources, namely Lambda and Function-url for lambda.
