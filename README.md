Creating a reference for use with nightbot to allow for an interactive fishing command that can show twitch users what they succeeded in catching
For reference; We can use the following code inside a Nightbot command to reference the fishing list. Nightbot commands are limited to 500 characters.

$(eval a=$(urlfetch json https://raw.githubusercontent.com/jmbrehm/nightbot-fishing-list/refs/heads/main/fish.json).fish;f=a[Math.floor(Math.random()*a.length)];w=parseFloat(f.weight);r=(w*(0.7+Math.random()*0.6)).toFixed(1);s=Math.abs((r-w)/w)<=0.15?"an average sized catch.":r<w*0.85?"kind of small...":"this one's HUGE!";g=Math.max(1,Math.round(f.rarity*r));`🎣 Congratulations $(user)! You caught a ${f.name} that weighs ${r} lbs! ${s} This is worth about ${g.toLocaleString()} gold pieces!`)
