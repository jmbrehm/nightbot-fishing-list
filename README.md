Creating a reference for use with nightbot to allow for an interactive fishing command that can show twitch users what they succeeded in catching
For reference; We can use the following code inside a Nightbot command to reference the fishing list. Nightbot commands are limited to 500 characters.

$(eval a=$(urlfetch json https://raw.githubusercontent.com/jmbrehm/nightbot-fishing-list/refs/heads/main/fish.json).fish;pool=[];a.forEach(f=>{for(i=0;i<f.count;i++)pool.push(f)});f=pool[Math.floor(Math.random()*pool.length)];w=parseFloat(f.weight);r=(w*(0.7+Math.random()*0.6)).toFixed(1);s=Math.abs((r-w)/w)<=0.15?"average sized catch.":r<w*0.85?"it’s small...":"HUGE!";g=Math.max(1,Math.round(f.rarity*r));`$(user)  caught a ${f.name}, weighing ${r} lbs! ${s}, Worth ${g.toLocaleString()} gold!` )
