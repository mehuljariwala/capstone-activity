**Please install .** 

`@nestjs/config`` and `dotEnv` and add this `app.module.ts` 

imports: [
    ConfigModule.forRoot({
        isGlobal: true, // Makes the module global
    }),

import * as dotenv from 'dotenv';
dotenv.config();


reason for this is you need to make sure to load the .env file please create .env file as well

.env => CLEAN_NEST_MONGO_CONNECTION_STRING=mongodb://localhost:27017 === for this run MongoDB composs == to download that follow this 

**How to install mangoDB || MongoDB composs **

https://www.youtube.com/watch?v=8gUQL2zlpvI&ab_channel=ProgrammingKnowledge


While exploring the code i found the another repo which is quite useful 

https://github.com/royib/clean-architecture-node/tree/master