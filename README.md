# POSTI-GRAPHQL

![pipeline status](https://posti-graphql.devaus.eu/pipeline.svg)
[![coverage report](https://posti-graphql.devaus.eu/coverage.svg)](https://posti-graphql.devaus.eu/coverage)
![latest version](https://img.shields.io/github/package-json/v/kirbo/posti-graphql.svg)
![last commit](https://img.shields.io/github/last-commit/kirbo/posti-graphql.svg)
![total downloads](https://img.shields.io/npm/dt/posti-graphql.svg)
![dependencies](https://img.shields.io/librariesio/github/kirbo/posti-graphql.svg)

## Description

`posti-graphql` extends [`posti`](https://www.npmjs.com/package/posti) by adding a GraphQL-server on top of it.

## Changelog

Check changes [here](./CHANGELOG.md).


## Installation

1. Install `posti`, [follow instructions here](https://github.com/kirbo/posti#installation-as-a-dependency-for-your-project).
2. Install `posti-graphql`
   ```
   yarn add posti-graphql
   ```
3. Create `npm` script for starting GraphQL server, in your `package.json`:
   ```
   "scripts": {
     "start-server": "posti-server"
   }
   ```
4. Start GraphQL server:
   ```
   yarn start-server
   ```
5. Play around, either in http://localhost:3000/graphql


## Demo
### Limitations

  - Timeframe: `24 hours`
  - Maximum `50` requests per IP within the timeframe.
  - `First 10` requests without delay.
  - After 10th request, delay every request with `+5 seconds from the previous`
    (`delay` = `delay + 5` -> 13th request = +15sec, 15th = +25sec...).

### Links
  - [Coverage report](https://posti-graphql.devaus.eu/coverage)
  - [First 100 rows from `Addresses`](https://posti-graphql.demo.devaus.eu/graphql?query=%7B%0A%09Addresses%20%7B%0A%20%20%20%20address%0A%20%20%20%20postOfficeName%0A%20%20%20%20postalCode%0A%20%20%7D%0A%7D)
  - [Search from `Addresses` where address begins with `mannerheim` and postOfficeName is `Helsinki`](https://posti-graphql.demo.devaus.eu/graphql?query=%7B%0A%20%20Addresses\(where%3A%20%7B%0A%20%20%20%20address%3A%20%22mannerheim%25%22%0A%20%20%20%20postOfficeName%3A%20%22Helsinki%22%0A%20%20%7D\)%20%7B%0A%20%20%20%20address%0A%20%20%20%20municipalityName%0A%20%20%20%20postalCode%20%20%20%20oddEven%0A%20%20%20%20smallestBuildingNumber1%0A%20%20%20%20highestBuildingNumber1%0A%20%20%7D%0A%7D)
  - [Search from `Addresses` where address begins with `turuntie` and building numbers are `odd`](https://posti-graphql.demo.devaus.eu/graphql?query=%7B%0A%20%20Addresses\(where%3A%20%7Baddress%3A%20%22turuntie%25%22%2C%20oddEven%3A%201%7D\)%20%7B%0A%20%20%20%20address%0A%20%20%20%20municipalityName%0A%20%20%20%20postalCode%0A%20%20%7D%0A%7D%0A)

  - [GraphQL Playground](https://posti-graphql.demo.devaus.eu/graphql)


## Disclaimer

I am not in any way affiliated with nor do I represent anything from [Finnish post - Posti](https://www.posti.fi/).


## License

MIT License

Copyright (c) 2018 Kimmo Saari

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
