# Iivineri Backend

Serviciu backend scris în Rust pentru platforma [Iivineri](https://github.com/iivineri-org/iivineri) - o aplicație care răspunde la întrebarea „Este azi vineri?".

![Rust](https://img.shields.io/badge/Rust-latest-orange.svg?logo=rust)
![Clap](https://img.shields.io/badge/Clap-CLI-blue.svg)
![SEO ORM](https://img.shields.io/badge/SEO_ORM-ORM-green.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-DB-blue.svg?logo=postgresql)
![Redis](https://img.shields.io/badge/Redis-Cache-red.svg?logo=redis)
![gRPC](https://img.shields.io/badge/gRPC-1.61-blue.svg)
![License](https://img.shields.io/badge/License-GNU--3.0-blue.svg)

## Arhitectură
```
┌─────────────────────────────────────────────────────────────────┐
|                             Browser                             |
└─────────────────────────────────────────────────────────────────┘
         ▲                                       ▲              
         │ HTTPs                                  │ HTTPs [GET]        
         ▼                                       ▼
┌─────────────────────────────────────────────────────────────────┐
│                         PUBLIC NETWORK                          │
|─────────────────────────────────────────────────────────────────|
│  ┌──────────────┐                    ┌─────────────────────┐    │
│  │  Frontend    │                    │   Thumbor (Image)   │    │
│  │   (Next.js)  │                    │      Service        │    │
│  └──────┬───────┘                    └─────────────────────┘    │
└─────────┼──────────────────────────────────────┼────────────────┘
          | gRPC                                 ▲
          ▼                                      │
┌─────────────────────────────────────────────────┼───────────────┐
│                        PRIVATE NETWORK          |               │
|─────────────────────────────────────────────────┼───────────────|
|  ┌──────────────┐                               |               |
│  │   Backend    │───────────────────────────────┘               │
│  │  (Rust-lang) │                                               │
│  └──────┬───────┘                                               │
│         │                                                       │
│    (DB, CACHE)                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Proiecte Conexe

- [Iivineri Frontend](https://github.com/iivineri-org/iivineri) - Aplicația frontend Next.js
