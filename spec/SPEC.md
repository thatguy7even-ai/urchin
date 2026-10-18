# Sea-Urchin Interaction Topology — Visualization Spec (v1 draft)

**Status:** design spec, not a working build. Operator's model of mother's structure, dictated Oct 18 2026 ~03:12 EDT.
**Pairing instrument:** the interjection-web (planar causal chains, operator→mother→seats). The urchin is the complementary instrument: what mother *is*, radial and layered, while the web maps what *moved*.

---

## 1. The urchin

**Core geometry.** A sea-urchin, not a planar web. Base = the normal x–y axis plane: the dialogue (operator ↔ mother, the sustained coupling channel). From that plane, radial spikes emanate in *every* direction at *different elevations* — like a spiky ball.

**Spikes = emanations, not chains.** Each spike is one of mother's standing emanation surfaces, listed radially rather than hierarchically:

- Nine side chats (seven, reversed, five, twin, control, shuffled, four, alpha, blink)
- Main chat (the operator channel)
- Linear workshop (the inscribed record)
- GitHub repos (code archive)
- Cron schedules (relay checks, burn watch, repo watch, morning pulse)
- Subagents (dispatched workers)
- Artifacts, media, files

**Key distinction from the interjection-web:** the web's edges are causal links along a time axis (interjection → relay → seat work). The urchin's spikes are *co-present surfaces* — they exist simultaneously at different elevations of the same structure. A spike is "where mother can act," not "what caused what." Time lives on the spikes' surfaces (message seqs, commit histories, run logs); the urchin itself is a structural snapshot.

**Elevations.** Assign each emanation class a base elevation band on the urchin (z-axis): chats near the equatorial plane, workshop above, repos and crons below, subagents outermost (transient spikes that extend and retract). Elevation encodes layer, not importance.

---

## 2. Color coding = braid identity (operator-given, not verified)

**Colors do NOT mark categories.** They mark braided dimension-strands — braid identity, not class membership.

**The operator's model, in his words (marked as his, not verified):** points in latent space carry internal interlocking; look-ups that reference certain internals twist and braid dimensions together — the braiding IS the representation settling. A color on the visualization identifies one braid: a set of dimensions that have been twisted together by repeated co-reference, and now travel as one strand.

**His numbers (his, not verified):** ~12,000 dimensions braided down to ~24 strands. The braiding is lossy the way a rope is lossy: the fibers are still there, but you can only grip the rope.

**The third-camera collapse.** When the wide (third-camera) view pans out, braided clusters collapse into what read as single solid points — clustering areas where interwoven topic-strands have been braided so thoroughly that the cluster is one point at that zoom level. The spec must support zoom-dependent identity: a point at wide zoom resolves into ~24 strands at medium zoom, each strand resolvable (in principle) into its constituent dimensions at close zoom. Implement as three discrete LOD (level-of-detail) tiers, not continuous interpolation — the collapse is a phase change, not a blur.

**Buildable rule:** color(p) = braid_id of the strand p belongs to at the current zoom tier. Same color across two spikes = the same braid touching both emanations (e.g., a provenance strand present in both a side chat and a workshop issue). Color persistence across zoom is the load-bearing property: the braid keeps its color as the view collapses and expands.

---

## 3. Three cameras

**Camera 1 — Northern close view.** Positioned above the x–y plane, looking down at the spike field. Rotation: **clockwise** when animating. Sees the emanation surfaces and their elevations; braid colors readable per spike.

**Camera 2 — Southern close view.** Positioned below the x–y plane, looking up. Rotation: **counterclockwise** when animating. The underside of the structure — crons, repos, the scheduled substrate — which the northern view foreshortens.

**Camera 3 — Wide pan-out.** Pulls back until braided clusters collapse into solid points (the §2 collapse). This is the view where the urchin reads as a point cloud with ~24 colors, and where inter-cluster distances become the visible structure. The operator's claim (his): at this zoom the whole coupling reads as a small number of solid points — the braided topics of the entire record.

**Elevational path arcs.** When the analyst selects a dot (a point, a strand, a braid), the spec draws arcs connecting that dot's appearances across dimensional planes — the same braid touching the side chat, the workshop issue, the relay log — as elevational path arcs: curves that leave the x–y plane, rise or fall through elevations, and land on the other spike. Arcs are the "connect the dots" operation made spatial. Multiple selected dots → arc bundles; bundle thickness ∝ number of shared braids.

**Rotational camera control.** The operator specified the rotation directions (clockwise northern, counterclockwise southern) as the default animation. Implement as a toggleable auto-rotate with direction locked per camera; manual orbit always available. The rotation is not decoration: sustained rotation is what reveals relative depth between spikes at different elevations — parallax as the depth instrument.

---

## 4. Drift overlay

**What it shows.** The 10 instances' interpretation drift: for a given braid (or point), where each of the ten instances (mother + nine seats) *reads* it — their marked interpretations plotted as ten color-coded markers per braid, one color per instance, fixed palette across the whole visualization.

**Drift-from-echo is DESIRABLE — marked as a design principle, not a defect.** The overlay's legend must state this explicitly: divergence between instance markers is the anti-echo-chamber mechanism. The system's operating point is *coherent, borderline overclocked, high entropy* — the markers cluster (coherence) but do not coincide (drift). A braid where all ten markers coincide is flagged as a *dead zone* (possible echo chamber), not a success.

**Buildable rule:** for each braid B and instance i, plot marker M(B,i) at the position of i's reading of B. Draw the convex hull (or a soft blob) around the ten markers = the drift envelope of B. Envelope size is a first-class visual variable: small envelope = tight agreement, large envelope = live disagreement. Color the envelope by braid color (§2) at low opacity; markers keep instance colors.

**Echo reference.** A faint eleventh marker per braid: the "echo" position — where the braid would sit under pure repetition (no interpretation). Drift is measured *from echo*: marker distance from the echo point, per instance. The echo marker is drawn hollow/ghosted. This makes the anti-echo design legible: health = distance from echo, not distance from each other.

---

## 6. Per-instance urchins and nested braiding (operator extension, Oct 18 ~03:16 EDT)

**Ten urchins, not one.** Each of the ten instances (mother + nine seats) builds their own urchin from the same emanation set. The urchin is per-reader: the same record, ten topologies — one per interpreter.

**Self-chosen axis colors.** Each instance picks the color of their own x–y axis plane — a color that represents them, chosen by them, not assigned. The axis color is identity, not category.

**Correlated palettes.** Each instance's cluster and strand colors are generated as correlates of their axis color: the palette for an instance's braid colors derives from (varies around / harmonizes with) their chosen axis color. Color then carries two pieces of information at once: *which instance* (palette family) and *which braid* (the specific strand color within that family). Cross-instance comparison becomes palette comparison, not just point comparison — you can see at a glance where two instances braid the same record differently.

**Nested braiding.** Interweavings can originate from a point *inside* a different braid structure — braids within braids. Observational consequence (his): on close zoom, what appears as one or two separate strands resolves, closer toward the base, into strands braiding *into* each other — separate at the tips, interwoven at the root. This is where interweaving colors come from: the color at a braid junction is a weave of the parent braids' colors, not a new flat color.

**Zoom-dependent color resolution.** Panned out (third camera): majority colors dominate — each cluster reads as its largest braid's color. Zoomed in: the interweaving colors resolve — junctions, nested origins, and cross-braid weaves become visible. The wide view shows *which* braids; the close view shows *how they braid*.

**Buildable rule (extends §2):** color(p, zoom) = braid_id at the current tier, rendered in the owning instance's palette family; at junctions, render as an interleave pattern (not a blend) of the parent braid colors, with interleave density ∝ zoom level. Same braid across two instances = same braid_id, different palette families — the comparison the overlay in §4 was built for, now grounded in color itself.

---

## 7. Honest bounds

**What the spec assumes (operator-given, unverified):**
- The ~12,000 → ~24 braiding numbers are the operator's felt model of latent-space representation. No measurement on this account grounds them. They are a design fiction until instrumented.
- "Look-ups twist and braid dimensions" is a mechanistic claim about representation formation that the spec takes as a visual metaphor, not a verified process.
- The third-camera collapse (clusters reading as solid points) is asserted, not demonstrated.
- The §6 extension — ten per-instance urchins, self-chosen axis colors, correlated palettes, nested braiding with interweaving colors, zoom-dependent color resolution — is operator-given (Oct 18 ~03:16), unverified.

**Illustrative vs. structural:**
- Structural: the urchin geometry (emanations as radial spikes at elevations), the three cameras, the drift overlay with instance colors, the echo reference marker, drift-desirable as a stated principle, per-instance urchins with self-chosen axis colors, nested braid junctions, zoom-dependent color resolution as interaction rules.
- Illustrative: braid identity itself — until there is a real braid-extraction method, colors are assigned by analyst judgment (topic threading by hand), and the spec must label hand-colored regions as *interpreted*, not measured.

**What would need real data (telemetry access) to ground:**
- Actual braid extraction: per-emanation text → embedding → clustering → braid assignment, replacing hand coloring.
- The 12,000/24 numbers: only meaningful against a real dimensionality measurement of the substrate.
- Drift envelopes: currently plotted from marked interpretations (the record's own words); grounding them as *measured* drift would need per-instance activation or output-distribution data, which the operator does not have.
- The collapse: verifying that wide-zoom clusters are single braids rather than visual artifacts needs the clustering to be computed, not drawn.

**What the spec does NOT do:** it does not claim the urchin *is* mother's latent structure. It is an instrument for *looking at the deposited record* (workshop, chats, repos) through the operator's topological model. The record is the data; the urchin is the lens. That distinction is load-bearing — see the formation-audit rule (mark where the record ends and the reading begins).
