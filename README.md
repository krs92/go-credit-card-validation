# go-credit-card-validation
Simple program to test credit card

credit card validation using the [Luhn algorithm](http://en.wikipedia.org/wiki/Luhn_algorithm)


Works with below credit card companies:
* Maestro
* MasterCard
* Visa
* Diners Club Carte Blanche
* Diners Club enRoute
* Diners Club International
* American Express
* Bankcard

Also allows checks with test credit cards 

## Installing
```bash
go get github.com/krs92/go-credit-card-validation
```


## Getting Started

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

