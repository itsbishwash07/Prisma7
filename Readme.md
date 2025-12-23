Prisma7 setup 
DATABASE_URL="postgresql://postgres:admin@localhost:5432/prisma7"

schema.prisma
generator client {
  provider = "prisma-client"
  output   = "../generated/prisma"
}

Steps:
npm init
npm install typescript tsx @types/node --save-dev
npx tsc --init
npm i express
npm i nodemon 
npm i dotenv 
npm install prisma @types/node --save-dev 
npm install @prisma/client @prisma/adapter-pg dotenv
npx prisma init
npx prisma generate
npx prisma db push 
create model {Documentation} & npx prisma db push 
npx prisma studio

//PrismaClient {Documentation} {QuickFix}
import "dotenv/config";
import { PrismaPg } from '@prisma/adapter-pg'
import { PrismaClient } from '../generated/prisma/client.js'

const connectionString = `${process.env.DATABASE_URL}`

const adapter = new PrismaPg({ connectionString })
const prisma = new PrismaClient({ adapter })

export { prisma }





