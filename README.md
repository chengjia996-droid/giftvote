# WHO WIN? gift-vote overlay (TikTok LIVE Studio, Add source > Link)

Files to host (static, any HTTPS host): dist/index.html (overlay) and dist/control.html (control panel). Both are self-contained; gift icons are embedded.

Overlay URL params: title, t (seconds), opts=2..6 (number of options, default 3), n1..n6 (names), g1..g6 (gift names: GG, Rose, It's corn, TikTok, Heart Me, Ice Cream Cone, Thumbs Up, Love you, Cake Slice, Finger Heart, Perfume, Doughnut, Hand Heart, Galaxy, or any name),
i1..i6 (custom icon URL), id1..id6 (gift id), coin1..6, mode=count|coins, pos=top|center|bottom, bg=0..1 (panel darkness),
src=euler|tikfinity|none, user (TikTok username), key (Euler API key), port (TikFinity port), room (control-panel code),
demo=1 (simulated gifts, auto loop), auto=1 (start on load), loop=N (auto restart N s after the round ends), debug=1 (status label), c1..c6 colors.

Default gifts: A=GG, B=Rose, C=It's corn, D=TikTok, E=Heart Me, F=Ice Cream Cone.
Default colors: A=#22d3c5, B=#ff4d8d, C=#b6f03c, D=#ff9f1c, E=#7c5cff, F=#3b9eff.
Existing 3-option links (no opts param) keep working unchanged.

Live gifts: Euler Stream WebSocket wss://ws.eulerstream.com?uniqueId=USER&apiKey=KEY, straight from the overlay (no install).
TikFinity Desktop Event API ws://localhost:21213 is supported too, but TikFinity Desktop is Windows-only.
Control panel -> overlay commands go through ntfy.sh topic giftvote_<room> (public relay, 250 messages/day per IP for free).
Combos: streakable gifts count by repeatCount delta per user+gift+groupId; duplicate msgIds ignored.

Winner logic: the option(s) with the highest vote count win. A single winner shows "Winner: X"; a tie with votes shows "TIE!"; 0 total votes shows "Voting closed" with no highlight.
