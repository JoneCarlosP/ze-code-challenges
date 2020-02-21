# Backend Challenge
> *Este arquivo também está disponível em português [aqui](backend_pt.md).*

In Zé we thrieve to find our best partner to delivery beverages to our customers, providing the best and fastest service.
To achieve this our compute fleet deal with GIS objects all the time.

When programming we try to follow a myrad of codding best practice and patterns (those you can read on books like Clean Code, Clean Arquitecture, The Pragmatic Programmer, Domain Driven Design, Microservice Patterns, etc...). 
Since writing **good code is a must** on our daily basis we expect people that want to join our team think alike. This code challange is something we designed to find this awesome programmers.

## 1. What we want you to do

We expect you to develop a service that provides an API using REST or GraphQL that can do the three following functionalities and technical requirements:

### 1.1. Create partner: 
Persist a partner defined by **all** the fields represented by the JSON and rules bellow:
```json
{
  "id": 1, 
  "tradingName": "Adega da Cerveja - Pinheiros",
  "ownerName": "Zé da Silva",
  "document": "1432132123891/0001",
  "coverageArea": { 
    "type": "MultiPolygon", 
    "coordinates": [
      [[[30, 20], [45, 40], [10, 40], [30, 20]]], 
      [[[15, 5], [40, 10], [10, 20], [5, 10], [15, 5]]]
    ]
  },
  "address": { 
    "type": "Point",
    "coordinates": [-46.57421, -21.785741]
  }
}
```

1. The `address` field follows the `GeoJSON Point` format (https://en.wikipedia.org/wiki/GeoJSON);
2. The `coverageArea` field follows the `GeoJSON MultiPolygon` format (https://en.wikipedia.org/wiki/GeoJSON);
3. The `document` must be a unique field;
4. The `id` must be a unique field;

You can use this [json](files/pdvs.json) file composed of hundreds of partners information to test your application.
Below, you can have a look on how these partners might be represented in a map:
![Partners in map](files/images/pdvs.png)

### 1.2. Load partner by id:
Return a specific partner by its `id` with all the fields presented above.

### 1.3. Search partner:
Given a specific location (coordinates `lng` and `lat`), search the **nearest** partner **which the coverage area includes** the location.

### 1.4. Technical Requirements:
* The programming language and the database engine it is entirely up to you;
* Your project must be **cross-platform**;
* Provide a documentation (README.md) file explaining how how to execute your service **locally** and how to deploy it (*focus on simplicity, and don't forget that we should test your service on our own, without further assistance*).

## Evaluation Method

We will evaluate your code challenge based on some *ilities.
Some we consider a must have, like **correctness** and will be evaluated on a boolean (works/follows or not) approach.
The others, since they are not that objective, will be evaluated by more then one developer and on a scale from 1 to 10.
This are all the *ilities that we expect you adress:
- **Correctness:** Your code must follow **all** the requirements presented on item [1.](#1-what-we-want-you-to-do);
- **Performance:** The more partners you can handle and the fastes you can query the best;
- **Testability:** How tested and how easy is to add tests to your code;
- **Maintanability:** How easy to add extra features to your code;
- **Separation of concerns:** (https://en.wikipedia.org/wiki/Separation_of_concerns)
- **Software engineering**<!-- TODO: O que queremos dizer com isso?-->

## How to deliver it

- Use Github private repositories to host your code and add @ze-engineering-code-challenge as a collaborator for it.
  This Github account (@ze-engineering-code-challenge) is solely used by Zé's engineers to download your code and review it.
- **Once you have finished the challenge, please submit your challenge information to this form:**
  https://docs.google.com/forms/d/e/1FAIpQLSePVCWxsHZHoRqJY9-XFJHuL7iOjO00sfhZksLBmDbR0KuoLg/viewform

Good luck!