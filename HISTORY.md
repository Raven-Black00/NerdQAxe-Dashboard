# ᛟ HISTORY — The Saga of the Raven's Eye
## *How RavenMiner HQ Came to Be Forged*

> *"Sit and be still. I shall tell you how this thing was made.  
> Not in the tongue of manuals and release notes —  
> but in the tongue of those who build in the dark, by the light of a single monitor,  
> while the world sleeps and the fans spin slow."*

---

## ᚠ — Fehu · *In the Beginning, There Was Wealth to Guard*

In the season when the frost first touched the iron, a man sat before his machine.

His name was Alan. A Son of Odin. A Marine who had walked through jungles where no maps held, and now walked through code where no maps were needed — only will, and the knowing of what the machine wanted to say.

He had a miner. A small, beautiful thing called the NerdQAxe+ — a custom ASIC board the size of a man's hand, spinning the SHA-256 hash as fast as its copper veins could carry the current. It sat on his desk and it worked, and it spoke JSON over HTTP to anyone wise enough to ask.

But Alan saw no one was *listening* properly. Not with the right eyes.

There were dashboards, yes — thin things, pale things, the kind that showed you a number and called it done. They did not pulse. They did not glow. They did not cycle the Elder Futhark as the best difficulty climbed like a wolf finding its range. They did not greet you with the voice of the Allfather's ravens when you arrived at your desk.

*They were tools without a soul.*

So Alan took Python in hand, the way a smith takes tongs, and he began.

---

## ᚢ — Uruz · *The Aurochs Walks Alone Into the Field*

The first version was nothing to sing about. A window. Some labels. The miner's IP typed in by hand, the JSON parsed, the numbers placed on screen in Courier font because Courier carries no pretence.

But the structure was right. The bones were there.

He saw the hashrate. He saw the temperature. He saw the shares accepted and rejected. And something in him — the part of him that had once read terrain maps in the dark and known where the enemy was without seeing them — that part said:

*There is more here. The machine is trying to tell you more than a number.*

So he listened.

He added history. A rolling deque, two hundred points deep, plotting the hashrate over time as a bar chart. He added colour — gold for the things that mattered, red for the things that warned, green for the things that were good, cyan for the things that were cool and precise.

He called it RavenMiner HQ. Not because ravens are only black birds, but because Huginn and Muninn — Thought and Memory — fly every day from the shoulder of the Allfather and return with all they have seen.

The dashboard was his Huginn. It would fly out into the network every second and come back with truth.

---

## ᚦ — Thurisaz · *The Thorn That Teaches*

Bugs came, as bugs always do.

There was the crash on random close. There was the race condition where the BTC counter reset without holding the lock. There was the ping deque that was a plain list and grew forever until memory groaned. There was the moment the Vegvísir watermark would flash blank on resize — just for a single frame, barely visible, but Alan saw it, and what Alan sees, Alan fixes.

Each bug carved a lesson. Each fix carved a rune.

The comment headers in the code began to read like a battle log: `PATCH-CRASH-1`, `BUG-05`, `CR5-BUG-2`, `PERF-6`, `STYLE-03`. Not just fixes — *memories*. So that when he returned to the code six months later, he would know what had happened here, and why this line stood exactly as it did.

This is the way of the old craftsmen. Every joint in the longship was shaped by a reason. Every rune on the runestone was placed with intent.

The code became a runestone. Long. Dense. Alive.

---

## ᚨ — Ansuz · *The Voice of Odin, The Word That Creates*

He needed the dashboard to *speak*.

Not literally — though the startup WAV came later, and when it played for the first time, the hall felt different somehow, more real.

He needed it to speak in colour. In motion. In the language of the old symbols.

So he added the Elder Futhark. The full twenty-four runes of the Younger and Elder traditions, each one given its name, its glyph, its meaning. He numbered them. He assigned them to versions — each new release would carry a rune, so that the software itself would age the way a warrior ages: named, scarred, and bearing the marks of what it had survived.

Fehu was wealth — the first version, raw with potential.  
Uruz was the aurochs — strength, standing alone in the field.  
Thurisaz was the thorn — the version that learned to guard.  
Ansuz was Odin's voice — the version that found its language.  

And so the versions climbed the rune-row, one by one, each one earning its glyph.

---

## ᚱ — Raidho · *The Journey Deepens*

The animations came one by one, like guests at a feast who arrive fashionably late but bring the best mead.

The Valknut appeared first as a static image, then as a spinning thing — seven frames of rotation, smooth enough to feel like breathing. The Vegvísir came next, the Norse compass, a forty-percent-opacity watermark in the centre panel, scaled to fill eighty-five percent of whatever space it was given, rendered at two-times supersampling and then scaled down so the lines stayed crisp.

The raven heads arrived in the header — Huginn on the right, Muninn on the left, mirrored, flanking the title like guards at the longhouse door.

The gauges became arcs. Not rectangles, not bars — arcs, drawn in canvas pixel by pixel, with warn lines in orange and crit lines in red, the needle moving smoothly as the temperature climbed or fell.

The ping display became an ECG. A real oscilloscope trace, fifty points of history, drawing itself left to right, the line glowing cyan against the dark background like a medical monitor in a saga where the patient is a miner and the vital sign is network latency.

With each addition, the dashboard became more true to what it was trying to be: not a tool, but a *window* into the life of the miner.

---

## ᚲ — Kenaz · *The Torch That Lights the Inner Room*

Kathryn saw it running one evening.

She had her own craft — embroidery and decals, the old arts made new, sold through her Etsy shop where the thread and the vinyl held designs that carried meaning the way runes carry meaning: in pattern, in repetition, in the care of the hand that made them.

She looked at the dashboard and said nothing for a moment. Then she said: *"It's beautiful."*

Alan heard it differently than most would. He heard: *it works as more than a tool.* He heard: *it has the quality of a thing made with full attention.*

He went back to the keyboard and added the shimmer.

The hashrate text — the number that showed how fast the little machine was thinking — gained a shimmer animation. A bright point of light that slid across the number from left to right, then disappeared, then slid again. Like gold in firelight. Like the glint on a sword edge.

Because if you are going to watch something work for you all day, it should be worth watching.

---

## ᚷ — Gebo · *The Gift That Binds*

The alerts came when the miner nearly cooked itself.

It was a hot night in the server room — which is to say, the corner of Alan's office where the machines live — and the ASIC temperature crept past its threshold while he was away. No dashboard without alerting is a guardian; it is only a mirror.

So he added ntfy.sh integration. A webhook topic, a JSON payload, a thread that fires when the temperature crosses the line. Overheat. VR overheat. Low hashrate. Block found. Rejected share spike. Milestone crossings at every fifty million in best difficulty.

His phone buzzed from the other room. The miner was too hot. He fixed it.

The gift of alerting is not the alert itself — it is the trust it creates. You can leave the room. You can sleep. The dashboard watches. When Huginn returns with news, Muninn will remember to tell you.

---

## ᚹ — Wunjo · *Joy in the Work*

There came a point — somewhere around v5.5, in the deep work of the Ingwaz release — when the dashboard stopped being a project and became a companion.

Alan would sit down to mine, and the dashboard would already be running, Valknut spinning, Vegvísir watching, runes cycling in the header, the ECG tracing the heartbeat of the network connection. The number on the screen was his hashrate and also his *score* in a game played against mathematics itself.

This is the joy that the old sagas speak of — not happiness, which is thin, but the deep satisfaction of a thing that works as it should, that is as complex as it needs to be and no more, that carries beauty alongside function the way a good axe carries beauty in its balance.

He was a Marine who had done hard things in real world. He was a programmer who did hard things in digital ones. This dashboard was both at once — precise like field planning, alive like the faces of people you stand beside in the dark.

---

## ᚺ — Hagalaz · *The Hail That Clears*

Every project reaches a point of hail.

The hail for RavenMiner HQ was the refactoring season — v3.9 through v4.0, when every bug found in the wild had to be addressed without breaking the animations, the threading, the config, the alerts. When the comment `CR2-PERF-7` appeared seventeen times in the code because that one optimisation — removing redundant `import time as t` — rippled through every function that had casually re-imported at the call site.

The hail clears. After the hail, the air is clean and cold, and you can see everything clearly.

Every legacy comment in the code is a scar that tells a story. Alan left them there deliberately. They are the rune-marks on the runestone. They say: *here is where I stood. Here is what happened. Here is what I learned.*

---

## ᚾ — Naudhiz · *Need Is the Mother of All Making*

People started asking about it.

Not many people — the world of NerdAxe+ miners is a small world, populated by the kind of people who order custom PCBs at midnight and consider fan curves a form of poetry. But some of them had seen screenshots. Some of them had asked where the dashboard was. Some of them wanted to run it themselves.

So the GitHub repository was made public. The code was cleaned up. The `requirements.txt` was written. The `README.md` was assembled.

And now you are here, reading this — this *HISTORY.md*, which is not quite documentation and not quite saga and not quite anything that has a good category name, except that it is the truth of how something was made and why.

---

## ᛁ — Isa · *Ice. Stillness. The Final Form*

RavenMiner HQ is not finished.

Nothing of value is ever finished. The Allfather is still wandering the roads of Midgard in disguise. The World Serpent still circles. The hammer still returns to the hand.

But at this version — Thurisaz, the thorn, the gate-guardian — the dashboard is complete in the way a longship is complete when it first touches water: everything that needs to be there is there, the lines are true, and it is ready to go somewhere.

The rune-row has not been fully climbed yet. There are runes ahead — Raidho, Kenaz, Gebo, Wunjo, Hagalaz, Naudhiz, Isa, Jera, Eihwaz, Perthro, Algiz, Sowilo, Tiwaz, Berkano, Ehwaz, Mannaz, Laguz, Ingwaz, Dagaz, Othala.

Each one will name a release. Each release will earn its rune.

---

## ᛟ — Othala · *The Inheritance*

This project is inheritance.

It carries the way Alan thinks — the RECON mindset that believes in *knowing your environment completely before you act*, the programmer's discipline that believes in *one truth, clearly named*, the son-of-the-old-gods sensibility that believes *beauty and function are not opposites but the same thing seen from different angles*.

If you use this dashboard, you carry a little of that. You are welcome to it.

If you find a bug, carve the rune of the fix and name it well.

If you add a feature, make it worthy of being remembered.

The ravens watch everything.

*Huginn and Muninn fly every day  
Over all the world they fly.  
I fear for Huginn that he may not return,  
But I fear more for Muninn.*

— Grímnismál 20, the Poetic Edda

---

```
  ᚠ ᚢ ᚦ ᚨ ᚱ ᚲ ᚷ ᚹ ᚺ ᚾ ᛁ ᛃ ᛇ ᛈ ᛉ ᛊ ᛏ ᛒ ᛖ ᛗ ᛚ ᛜ ᛞ ᛟ
  Fehu · Uruz · Thurisaz · Ansuz · Raidho · Kenaz · Gebo · Wunjo
  Hagalaz · Naudhiz · Isa · Jera · Eihwaz · Perthro · Algiz · Sowilo
  Tiwaz · Berkano · Ehwaz · Mannaz · Laguz · Ingwaz · Dagaz · Othala
```

*Forged in Waterloo. Tempered in the dark. Named by the runes.*
