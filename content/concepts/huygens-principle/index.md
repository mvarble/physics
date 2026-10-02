---
title: Huygens' Principle
depends_on: [wave-nature-of-light]
---

This document builds on [Wave nature of light](../wave-nature-of-light/).

Huygens' principle is a geometric and mathematical method for predicting how a wave propagates. Proposed by Christiaan Huygens in 1678 in his *Traité de la lumière*, it provides a recipe: given the shape and amplitude of a wavefront at one instant, the wavefront at any later instant can be constructed by treating every point on the original front as a source of secondary wavelets and finding their envelope. This principle is remarkable because it reduces the complex problem of wave propagation to a straightforward geometric construction — and it works for all waves, not just light. Sound waves, water waves, and seismic waves all obey Huygens' principle.

## The core idea

The principle states that **every point on a wavefront acts as a source of secondary spherical wavelets**, each expanding at the wave speed $c$. After some elapsed time $\Delta t$, the new wavefront is the surface tangent to all of these wavelets — their envelope.

Consider a plane wave, a flat wavefront, moving to the right. At time $t = 0$, every point on that flat front emits a spherical wavelet. After time $\Delta t$, each wavelet is a sphere of radius $c\,\Delta t$. The surface tangent to all of these spheres from the forward side is a new flat plane, displaced to the right by $c\,\Delta t$. The plane wave propagates as a plane wave, exactly as expected.

Now consider a wavefront that encounters an obstacle or passes through a slit. The points on the wavefront blocked by the obstacle do not emit wavelets — the obstacle absorbs or reflects them. Only the unobstructed points continue to radiate. The envelope of the surviving wavelets is no longer a simple plane or sphere. It curves around the edges of the obstacle, spreading into what geometric optics calls the shadow region. This spreading is the phenomenon of diffraction, and Huygens' principle provides the mechanism that explains it.

## Deriving the laws of reflection and refraction

Huygens' principle is powerful enough to derive the basic laws of geometric optics without any further assumptions. This was, in fact, its original purpose.

**Reflection.** A plane wave strikes a flat mirror at angle $\theta_i$ measured from the normal. As the wavefront contacts the mirror, each point of contact becomes a source of a reflected wavelet expanding back into the original medium at speed $c$. The envelope of these reflected wavelets is a plane wave traveling away from the mirror. A simple geometric argument shows that the reflected wavefront makes the same angle with the normal as the incident wavefront: $\theta_r = \theta_i$. The law of reflection follows directly.

**Refraction.** A plane wave passes from a medium where the wave speed is $c_1$ into a medium where it is $c_2 < c_1$ (a denser medium). As the wavefront reaches the interface, each contact point emits a wavelet into the second medium, but these wavelets expand more slowly. The envelope of the slower wavelets is tilted relative to the original wavefront, bending the direction of propagation toward the normal. The geometry yields

$$
	\frac{\sin\theta_1}{\sin\theta_2} = \frac{c_1}{c_2}
$$

which is Snell's law, with the refractive index $n = c / c_{\text{medium}}$. Huygens published this derivation in 1678, and it remains one of the most elegant explanations of refraction.

## The Huygens–Fresnel formulation

Huygens' original principle was geometric and qualitative — it described wavefronts but did not compute amplitudes or phases. Augustin-Jean Fresnel, in the 1810s, placed the principle on a firm quantitative footing by incorporating the wave properties of amplitude and phase. In the Fresnel formulation, the complex amplitude at an observation point $P$ due to a monochromatic wavefront is

$$
	\tilde{E}(P) \propto \iint_{\text{wavefront}} \frac{e^{ikr}}{r} \, K(\theta) \, dS
$$

where $r$ is the distance from each point on the wavefront to $P$, and the integral runs over the unobstructed portion of the wavefront. The factor $e^{ikr}/r$ is the spherical wavelet from the [wave nature of light](../wave-nature-of-light/): it captures both the $1/r$ amplitude decay and the $kr$ phase accumulation. The function $K(\theta) = \frac{1}{2}(1 + \cos\theta)$ is the **obliquity factor**, which weights each wavelet by the angle $\theta$ between its propagation direction and the outward normal to the wavefront. This factor equals $1$ in the forward direction and $0$ in the backward direction, eliminating the backward-propagating wave that the naive principle would otherwise predict.

Gustav Kirchhoff later derived this integral rigorously from the wave equation using Green's theorem, confirming that Huygens' principle is not merely a heuristic but an exact consequence of the wave equation (in three dimensions, for monochromatic waves).

## Illustrative example: wave propagation through a slit

To see Huygens' principle at work in a concrete situation, consider a plane wave illuminating a narrow slit of width $a$ in an opaque screen. By the principle, every point across the open slit emits a spherical wavelet.

At a point $P$ directly ahead of the slit center, all wavelets travel the same distance (in the limit of a distant screen) and arrive in phase. Their amplitudes add constructively, producing a bright region. At a point $P$ displaced to one side, wavelets from different positions across the slit travel different distances. Wavelets from the far side of the slit travel farther than wavelets from the near side, and therefore arrive with a phase lag. When the path difference across the full slit width is exactly one wavelength $\lambda$, the wavelet from the top of the slit is one full wavelength ahead of the wavelet from the bottom. The wavelet from the midpoint is half a wavelength ahead. Pairing each wavelet in the top half with a wavelet half a slit-width below it, every pair is separated by a half-wavelength path difference and interferes destructively. The total amplitude at $P$ is zero — a dark fringe.

This qualitative reasoning captures the essential mechanism: Huygens' principle converts the problem of wave propagation past an obstacle into a superposition of spherical wavelets, and the path-length differences among those wavelets determine where the result is bright and where it is dark. The full quantitative treatment of this calculation — integrating over the slit and deriving the complete intensity pattern — is the subject of [diffraction of light](../diffraction-of-light/).

## Huygens' principle in three dimensions

An important subtlety concerns the dimensionality of space. In three dimensions, the spherical wavelets from Huygens' construction produce sharp wavefronts: a brief pulse emitted at one point arrives at a distant point as a brief pulse, with no lingering wake. This is a consequence of the exact cancellation of backward-propagating contributions, formalized by the obliquity factor. Sound in air behaves this way — a sharp clap is heard as a sharp clap at a distance, not as a drawn-out rumble.

In two dimensions (surface waves on a pond, for instance), the analogous construction uses circular wavelets rather than spherical ones, and the cancellation is not exact. A pulse produces a wake that persists after the leading edge passes — the ripples that trail behind a stone dropped in water are a manifestation of this two-dimensional Huygens behavior. This distinction between even and odd spatial dimensions is formalized in the mathematics of the wave equation's Green's function and is sometimes called the **strong Huygens principle** (exact in 3D) versus the **weak Huygens principle** (approximate in 2D).

## Significance

Huygens' principle occupies a central place in wave physics. It provides a unified geometric framework for understanding reflection, refraction, and diffraction — phenomena that geometric optics treats as separate rules. It was the key insight that allowed Fresnel to predict and explain diffraction patterns quantitatively, settling the long debate between the wave and particle theories of light in the wave theory's favor. In modern physics, the principle generalizes into the mathematical machinery of Green's functions and propagators, which are the foundation of quantum field theory and the theory of wave scattering.

See also: [Diffraction of light](../diffraction-of-light/)
