<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Luxury
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Luxury is becoming something for everyone as much as possible. Big luxury brands are partnering with influencers to drive more interest in luxury products and increase the share of wallet. Anyone positioned as a luxury brand can win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| AAPL | Apple's premium products and collaborations with luxury brands position it well within the luxury tech space. | chat_gpt,twitter |
| CPRI | Capri Holdings, owner of Versace, Michael Kors, and Jimmy Choo, can leverage influencer partnerships to enhance its luxury appeal. | chat_gpt,claude,google |
| EL | Estée Lauder, with its high-end beauty products, stands to gain from the growing luxury market and influencer collaborations. | chat_gpt,claude,google |
| GOOS | Canada Goose could leverage its high-end outerwear status and influencer endorsements to capture more of the luxury market. | chat_gpt,claude |
| HSY | Hershey's ownership of artisan chocolate brands could benefit from the luxury trend through premium product offerings. | chat_gpt |
| NKE | Nike's collaborations with luxury brands and influencers can further elevate its products into the luxury sportswear segment. | chat_gpt,claude |
| PVH | PVH Corp., with luxury brands like Calvin Klein and Tommy Hilfiger, can utilize influencer partnerships to boost its luxury profile. | chat_gpt,google |
| RL | Ralph Lauren, with its classic luxury appeal, can gain from increased luxury consumption and influencer marketing strategies. | chat_gpt,claude,google |
| SFIX | Stitch Fix's personalized styling service could capitalize on the growing demand for luxury and designer wear through influencer partnerships. | chat_gpt,claude |
| TSLA | Tesla's brand as a luxury electric vehicle maker positions it to benefit from the luxury trend, especially with celebrity endorsements. | chat_gpt,twitter,google |
| FWONK |  | claude |
| LEVI |  | claude |
| REAL |  | claude |
| RVLV |  | claude |
| TPR |  | claude,google |
| URBN |  | claude |
| AZO |  | twitter |
| EBS |  | twitter |
| HD |  | twitter |
| LOW |  | twitter |
| LULU |  | twitter |
| RH |  | twitter,google |
| CFR |  | google |
| HOG |  | google |
| IPAR |  | google |
| JWN |  | google |
| WSM |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/luxury/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/luxury" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
