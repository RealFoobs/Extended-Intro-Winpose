# Extended-Intro-Winpose

`intro-outro.zss` is a user friendly script meant to overwrite the default behavior of HUD elements (i.e. lifebars) and stage music during character intros, in the immediate aftermath of a KO and while characters enter their winposes. The idea is to give the end user the ability to replicate the aesthetics of most commercial games, which tend to have more dynamic interactions than what Ikemen inherited from the MUGEN engine.

**To install**

1. Drop the contents of the most recent release in your `data\` folder.
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
You just need to add `"data/intro-outro.zss"` and `"data/intro-outro-config.zss"` so the engine can read the files.

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
  The order isn't very relevant, just make sure to include a comma if either file is NOT the last the last line on the block, and to ommit it if it isn't.
  
  4. Go back to `data\` and open `intro-outro-config.zss`, if windows does not recognize the file extension open it with any text editor (I'd recommend Notepad++) and read the specific instructions as to what each feature does and how to enable it.

**Features**

1. io_intro_skip

Makes intros unskipabble. Mashing buttons during the intro will do nothing. Might lock some characters that have poorly made pre-fight select systems.

2. io_pow_r1

Controls how much power both characters receive at the beginning of the fight. Games like Marvel vs Capcom and Melty Blood give the characters 1 stock of meter at the beginning of the fight, as to not make them start with any resources. You can put however much power you want to, even 3 full stocks like Street Fighter Alpha 3 does. Just keep in mind that this cannot override the maximum power defined by a character's constants.

3. io_pow_wi

Controls how much power the winner of the previous round receives at the beginning of the current one. Sounds like an odd mechanic, given that most games do not want the player in the lead to snowball into an easy match game by giving him more resources, but there's another use for it: you can pick a negative number. Using this and io_pow_lo you can reproduce the behavior of games like Super Turbo where the powerbar does no carry into the following round.

4. io_pow_lo

Controls how much power the loser of the previous round receives at the beginning of the current one. You can use this as comeback mechanic, similar to how games like MB Type Lumina gives you a free bar of super after losing a round. Or as stated above, you can also drain the character's meter by using a negative value.

5. io_pow_tm

Essentially the same as io_pow_lo, but for team mode specifically. You can set it to work like The King of Fighters 98's emotion system (minus RNG), by using either positive or negative values.

6. io_intro_bgm_r1

Mutes the music during the intro phase of round 1, so you can hear the characters' intro lines better. Note that unlike commercial games where music plays after the characters' intros, in Ikemen it'll start playing at the beginning of the round at 0 volume, meaning that it might ruin the atmosphere in stages that have their own special intros.

7. io_intro_bgm_tm

Essentially the same as io_intro_bgm_r1, but triggers every time a new character enters the fight in turn mode, like in KOF.

8. io_intro_hud_r1

Hides the lifebars during intros in round 1. They'll be visible as soon as the characters can be controlled by players.

9. io_intro_hud_rx

Does the same as io_intro_hud_r1 on round 2 onwards.

10. io_intro_hud_tm

Essentially the same as io_intro_hud_r1, but triggers every time a new character enters the fight in turn mode, again, like in KOF.

11. io_ko_slo

Removes the standard slowdown during KOs. Note that you could also change this directly from the lifebar.

12. io_ko_spc

Creates a simple ko effect with red and white flashes (like in KOF) when the round is won with a special attack. Minor seizure warning.

13. io_ko_sup

The same effect as io_ko_spc, but only triggers for supers. Both are independent given how many characters have their own super KO background.

14. io_ko_bgm

Mutes the background music during KOs. It will resume playing shortly afterwards, unless you also use io_win_bgm.

15. io_ko_hud

Hides the lifebars during KOs, like in KOF. They'll be visible shortly afterwards, unless you also use io_win_hud.

16. io_win_skip

Does the same as io_intro_skip, but for winposes.

17. io_win_bgm

Mutes the background music once the characters start their winposes.

18. io_win_hud

Hides the lifebars once the characters start their winposes. Might want to keep this one active to be able to check how much power the characters have left for the next round.

19. io_win_cam

Focus and zooms the camera once the fight ends, inspired by SNK games like AOF or SamSho. Has three settings: 0) keeps the camera static (default behavior), 1) zooms on the winner and 2) zooms on he loser.

20. io_win_zoo

Determines how much the camera should zoom on the characters, if io_win_cam is enabled. Values over 1.50 may look very off. Values under 1.0 are ignored.
