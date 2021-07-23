# Model Comparison Format

The comparison files provided give the description of a span (maps from one
*apex* model to potentially several other models). This description is provided
in a `json` file with the following format:
```json
{
  "apex": "SimpleSIR_PetriNetClassic",
  "legs": {
    "SimpleChime+PetriNetClassic": [
      {
        "J:gamma": "J:rec_u",
        "J:I": "J:I_U",
        "J:R": "J:R",
        "J:S": "J:S",
        "J:beta": "J:inf_uu"
      },
      {
        "J:gamma": "J:rec_v",
        "J:I": "J:I_V",
        "J:R": "J:R",
        "J:S": "J:V",
        "J:beta": "J:inf_vv"
      }
    ]
  }
}
```
The structure is as follows:
- *apex*: The UID of the apex model
- *legs*: The list of models which have maps from the apex model
	- *ModelUID*: A list of all structure-preserving maps from ModelUID to the apex model
		- *Maps*: These arrays are maps by UID of elements from the apex to elements of the ModelUID model.
