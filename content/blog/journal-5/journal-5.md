---
title: "Journal 5: Multiplayer Mishap"
description: "A check-in for the 5th week."
date: 2026-09-28
---

## Tasks Worked On

Yayyy more [commits](https://github.com/KxtR-27/CS414_VipWaveSurvival/commits?since=2026-09-21&until=2026-09-27&author=KxtR-27).
And this time, a [PR](https://github.com/KxtR-27/CS414_VipWaveSurvival/pull/1), too.

- Local multiplayer input handling overhaul
- Aiming your attacks
- Process check optimizations

## Time Estimation

I had a migraine on Monday so laying in bed, dazed and confused, I had quite a bit of time to work on things slowly.
I estimated this stuff would take four hours. It did.
The multiplayer input stuff both felt like it took forever and like it happened quickly.
Blame it on the migraine.

## Struggles

Ooohh, basic trigonometry.
Aimable hurtboxes was rough for going from vectors to angles to radians to degrees to directions to--
You get the idea.

Eventually I settled on a system that can both

1. Point at a specific target/Node2D

```gdscript
func aim_at_body(body: Node2D) -> void:
	self.rotation = self.global_position.direction_to(body.global_position).angle()
```

2. Aim in a certain direction(al vector).

```gdscript
func aim_in_dir(direction: Vector2) -> void:
	self.rotation = direction.angle()
```

The first method is how enemies aim their hurtboxes at a given target as they're chasing them.
The second method is how players aim their hurtboxes using the mouse or the right joystick.

## Team Problem

This is a struggle, but putting it here is more important.

While things on the team have been going generally well,
there was an issue with my overhaul of the multiplayer input system:
I overwrote Alex's code and barely asked.
Not very nice of me, even though I meant well.

Here's the best way I can put it, and how I did put it for milestone 1.

> There was a hiccup, though. Throughout the whole past weekend (starting on Friday, September 25th),
> Alex worked hard on a local multiplayer input system.
> By Monday, it was only partially functional.
> Kat, anxious to have something viable for Milestone 1,
> let Alex know that she was working on a safer implementation without asking beforehand if Alex was okay with that.
> Alex, a little blindsided, said it sounded good, so Kat took that as permission to continue.
> Kat then… overwrote all of Alex’s work without considering that it meant a lot to him,
> and again without asking.
> Kat and Alex worked it out well in the end, and the interaction brought to light a need to set collaborative boundaries.
> Both the conflict and the resolution were healthy and without animosity,
> and we are in a better place collaboratively as a result.

It was largely a misunderstanding. Now I always ask Alex how I can help first.
This lets us work out a solution that still preserves the effort and meaningfulness of the hard work Alex does.
