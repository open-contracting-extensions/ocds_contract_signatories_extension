# Contract signatories

Adds a signatories array to the contract object, for when the signatories differ from the buyer for the contracting process and the suppliers for the award.

In OCDS, the signatories to a contract are not explicitly declared in the `contracts` section. Instead, the signatories are implicitly assumed to be the `buyer` and the `suppliers` in the award associated to the contract.

In some types of contracting processes, there can be additional signatories to the contract, or the signatories to the contract can differ from those specified in `buyer` and `suppliers`.

Use this extension **only if** the signatories to a contract differ from its related award's `suppliers` and the contracting process' `buyer`. If that is the case, list all signatories to the contract, including the `buyer` and `suppliers`.

## Guidance

Each signatory should have an associated entry in the `parties` section.

## Example

The following JSON snippet models a contracting process where there is an additional signatory to the contract beyond those defined in the `buyer` and `awards.suppliers` fields.

```json
{
  "buyer": {
    "name": "Ministry of Communications",
    "id": "GB-GOV-12345678"
  },
  "awards": [
    {
      "id": "1",
      "suppliers": [
        {
          "name": "Example Consortium",
          "id": "GB-COH-00000000"
        }
      ]
    }
  ],
  "contracts": [
    {
      "id": "1",
      "awardID": "1",
      "signatories": [
        {
          "name": "Ministry of Communications",
          "id": "GB-GOV-12345678"
        },
        {
          "name": "Example Consortium",
          "id": "GB-COH-00000000"
        },
        {
          "name": "Telecommunications UK",
          "id": "GB-GOV-99999999"
        }
      ]
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2020-04-24

* Add `minProperties`, `minItems` and/or `minLength` properties.
