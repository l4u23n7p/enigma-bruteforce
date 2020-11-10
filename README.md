# enigma-bruteforce

This small script tries to find a enigma setting encrypting known plaintext into known ciphertext.

Brian Neal's Py-Enigma library is used to simulate the enigma. All possible combinations are bruteforced. Note that is unlikely to find a working combination using this strategy if the plaintext and ciphertext are somewhat longer than five characters each.

Example:

```
$ python3 main.py --plaintext=GITHUB --ciphertext=PYJAMA
```

This outputs (after a while of searching):

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Solution found! Encrypt GITHUB to PYJAMA
{'ref': 'B', 'plug': 'AB CD EF GL HJ IN KO MP QT RS ', 'rotor': ('I', 'II', 'III'), 'ring': [0, 0, 0], 'display': 'HLR'}
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

## Settings

Known parameters can be passed to reduce the possibilities.

| Option       | Value                                                                                                                                            | Example                              |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------ |
| `rotors`     | List of rotor to use. At least 3 are needed.                                                                                                     | `--rotors II IV VI VIII`             |
| `reflectors` | List of reflector to use. More details on [py-enigma docs](https://py-enigma.readthedocs.io/en/latest/reference.html#reflector-table-label).     | `--reflectors A B`                   |
| `ring`       | String either space separated letters or numbers. Note that if numbers are used, they should be between 1-26 to match historical key sheet data. | `--ring 'A B C'` or `--ring '0 1 2'` |
| `plugboards` | Number of plugboard to guess                                                                                                                     | `--plugboards 2`                     |

## Dependencies

```
Py-Enigma
```
