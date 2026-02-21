---
layout: page
title: Tapahtumat
permalink: /tapahtumat/
---

Tervetuloa mukaan retkille ja muihin tapahtumiin! Voit suodattaa tulevia tapahtumia eri toimintamuotojen perusteella, valitsemalla alta sinua kiinnostavan toimintamuodon.

Retkillemme olemme luoneet vaativuusluokitukset. Voit tutustua luokituksiin [tästä (PDF)](https://helsinginlatu.fi/wp-content/uploads/2023/04/HeLaPo_paivaretkien_vaativuusluokitus.pdf){:target="_blank"}.

Kaikkiin toimintamuotoihimme voit tutustua tarkemmin [Tule mukaan -osiossa](/tule-mukaan/). Toimintaan voi tulla mukaan kokeilemaan, vaikka et vielä olisi jäsen.

## Löydä oma tapasi ulkoilla

<div class="activity-pills">
  <a href="/tapahtumat/" class="activity-pill">Kaikki</a>
  <a href="/tapahtumat/?filter=hiihto" class="activity-pill">Hiihto</a>
  <a href="/tapahtumat/?filter=keppijumppa" class="activity-pill">Keppijumppa</a>
  <a href="/tapahtumat/?filter=kurssit" class="activity-pill">Kurssit</a>
  <a href="/tapahtumat/?filter=lauluillat" class="activity-pill">Lauluillat</a>
  <a href="/tapahtumat/?filter=lentopallo" class="activity-pill">Lentopallo</a>
  <a href="/tapahtumat/?filter=polkujuoksu" class="activity-pill">Polkujuoksu</a>
  <a href="/tapahtumat/?filter=paivakavelyt" class="activity-pill">Päiväkävelyt</a>
  <a href="/tapahtumat/?filter=talviuinti" class="activity-pill">Talviuinti</a>
  <a href="/tapahtumat/?filter=kokous" class="activity-pill">Kokous</a>
  <a href="/tapahtumat/?filter=maastopyoraily" class="activity-pill">Maastopyöräily</a>
  <a href="/tapahtumat/?filter=retkeily" class="activity-pill">Retkeily</a>
</div>

<div class="events-list">
{% for event in site.data.events %}
<div class="event-item">
  <div class="event-date-box"><span class="day">{{ event.day }}</span><span class="month">{{ event.month }}</span></div>
  <div class="event-info"><h3><a href="{{ event.url }}" target="_blank" rel="noopener">{{ event.title }}</a></h3></div>
</div>
{% endfor %}
</div>
