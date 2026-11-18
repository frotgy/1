await initHydra()

s0.initImage('https://freight.cargo.site/w/1500/q/75/i/T2829677372114869979643705207132/166.png')
src(s0).modulate(osc(5, 0.2), 0.5).out()

$: s("bd(3,8) [hh oh]*2")
  .bank("SimmonsSDS5")
  .degradeBy(0.25) 
  .sometimesBy(0.3, x => x.ply(2))
  .vowel("<e a o i>")
  .gain(1.5)

$: s("gigi")
  .slow(3)
  .degradeBy(0.45)
  .sometimesBy(0.3, x => x.ply(2))
  .room(0.9)
  .gain(6)

$: n(irand(10).fast(2))
  .add(choose(0, 7, -7))
  .scale("C5:major:pentatonic")
  .sound("triangle")
  .lpf(4500)
  .degradeBy(0.35)
  .sometimesBy(0.3, x => x.ply(2))
  .pan(rand)
  .room(0.8)
  .gain(5)
  

$: s("viscospacedrum_perc:2*12")
  .slow(6)
  .degradeBy(0.45)
  .sometimesBy(0.35, x => x.ply(4))
  .rarely(x => x.ply(16).speed(1.8).dec(0.03))
  .speed(perlin.range(0.1, 4))
  .dec(rand.range(0.02, 0.15))
  .hpf(rand.range(600, 3000))
  .hpq(10)
  .pan(rand)
  .room(0.9)
  .gain(3)

$: s("pink")
  .lpf(sine.range(200, 1400).slow(3))
  .room(0.8)
  .gain(0.4)
  .color('#ff66b2')
  .scope({
    thickness: 18,
    scale: 1.8,
    pos: 0.75
  })
