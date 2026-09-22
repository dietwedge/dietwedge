# dietwedge.com

One bottle in a dim room. Turn it around.

Diet Wedge was a grapefruit soda in Wegmans' W-Pop line, since discontinued.
It was the can on the desk the day a screen name was needed, and the name
outlived the soda. This is the page that name points to.

## What is here

| | |
|---|---|
| `index.html` | the whole page — markup, styles, the label, the script |
| `bottle.webp` | the glass, 834×2595, 148 KB, what the page actually loads |
| `source/bottle-v1.png` | the original render, 1520×2688, for re-cropping |

Deployed by `vps/sync-static.sh dietwedge-landing dietwedge.com` from the
`ai-business` working tree. `source/` and this README are excluded from what
gets published.

## How it is built

**The glass is a photograph.** Generated with Higgsfield, GPT Image 2,
`--aspect_ratio 9:16 --resolution 2k`, from this prompt:

> Photoreal product photograph of a single 20 fl oz green PET plastic soda
> bottle, straight-on at eye level, centered, filling most of the frame
> vertically. Translucent pale green plastic with faint carbonated pale-green
> liquid filled up to the shoulder, visible meniscus. Clear ribbed plastic
> screw cap with a thin green tamper ring. A completely BLANK matte silver
> label band wraps the lower two-thirds of the body — no text, no logo, no
> graphics, no printing of any kind, plain brushed silver. Studio lighting:
> one soft warm key light from the upper left, a long specular highlight down
> the left edge of the bottle, subtle rim light on the right. Solid pure black
> background, no floor, no table, no reflection, no shadow on the ground,
> nothing else in frame. Sharp, high detail, commercial beverage photography.

The blank band is the point: the label is not in the image.

**The label is a cylinder of real text.** Forty narrow faces stand around the
body, each rotated nine degrees further than the last and each showing its own
slice of one continuous strip — the front design on one half, the Nutrition
Facts on the other. Turning the bottle rotates the cylinder. The silver halves
are transparent, so the photo's own brushed metal and lighting show through;
only the printed panels are painted on top.

The band's position is measured from the pixels, not eyeballed. In the crop it
sits 36.38% down, is 46.32% tall, and spans 88.25% of the width starting at
5.88%. If the render is ever replaced, re-measure and update `.wrap`.

**The black background blends away** with `mix-blend-mode: screen`. That only
works if nothing between the `<img>` and `<body>` creates a stacking context —
`container-type`, `filter`, `z-index` and `opacity` all do — which is why the
image is a sibling of the label stage rather than inside it, and why the drop
shadow is a blurred ellipse instead of a filter.

Everything on the label is sized in `cqw`, the stage's width, so it scales
with the bottle from a phone to a desktop with no breakpoints.

**The privacy story is short because it is true:** one external resource (the
Lobster font from Google Fonts), no cookies, no storage, no analytics, no form.

## Not affiliated with Wegmans

The name was theirs. They stopped making it. The W logo is deliberately not
used anywhere on the page.
