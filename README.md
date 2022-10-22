# Extended-Intro-Winpose

`intro-outro.zss` is a user friendly script meant to overwrite the default behavior of HUD elements (i.e. lifebars) and stage music during character intros, in the immediate aftermath of a KO and while characters enter their winposes. The idea is to give the end user the ability to replicate the aesthetics of most commercial games, which tend to have more dynamic interactions than what Ikemen inherited from the MUGEN engine.

**To install**

1. Drop `intro-outro.zss` and `intro-outro-config.zss` in your `data\` folder.
2. Go to `save\` and open `config.json`
3. Near the beginning of the file you should see a block like this:

```
	"CommonStates": [
		"data/action.zss",
		"data/dizzy.zss",
		"data/guardbreak.zss",
		"data/score.zss",
		"data/tag.zss",
		"data/training.zss"
	],
```
You just need to add the line `"data/intro-outro.zss"`so the engine can read the file.

```
	"CommonStates": [
		"data/action.zss",
		"data/dizzy.zss",
		"data/guardbreak.zss",
		"data/score.zss",
		"data/tag.zss",
		"data/intro-outro.zss",
		"data/intro-outro-config.zss",
		"data/training.zss"
	],
  ```
  The order isn't very relevant, just make sure to include a comma if it is NOT the last the last line on the block, and to ommit it if it isn't.
  
  4. Go back to `data\` and open `intro-outro-config.zss`, if windows does not recognize the file extension open it with any text editor (I'd recommend Notepad++) and read the specific instructions as to what each feature does and how to enable it.
