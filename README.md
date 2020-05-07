# Credit Card

Basic credit card validation using the [Luhn algorithm](http://en.wikipedia.org/wiki/Luhn_algorithm)


| Date | Author | Comments | Version |
| --- | --- | --- | --- |
| 02/03/2019 | Wagner aka Barão | This is the Beginning of success | 0.0.1 |

Currently identifies the following credit card companies:

- American Express
- Aura
- Bankcard
- Cabal
- China Unionpay
- Dankort
- Diners Club Carte Blanche
- Diners Club enRoute
- Diners Club International
- Discover
- Elo
- Hipercard
- InterPayment
- InstaPayment
- JCB
- Maestro
- MasterCard
- Naranja
- Visa
- Visa Electron

## Installation

```bash
    go get github.com/wagner-aos/credit-card
```

## Quick Start

```go
// Initialize a new card:
card := creditcard.Card{Number: "4242424242424242", Cvv: "11111", Month: "02", Year: "2016"}

// Retrieve the card's method (which credit card company this card belongs to)
err := card.Method() // card.Company({Short: "visa", Long: "Visa"})

// Display last four digits
lastFour, err := card.LastFour() // 4242

// Validate the card's number (without capturing)
err := card.Validate() // will return an error due to not allowing test cards

err := card.Validate(true) // this will work though
```
