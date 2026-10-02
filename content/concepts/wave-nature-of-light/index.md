---
title: Wave Nature of Light
---

Light is an electromagnetic wave: oscillating electric and magnetic fields that propagate through space at speed $c \approx 3 \times 10^8 \text{ m/s}$ in vacuum. This wave model explains a wide range of optical phenomena that a particle model cannot — the colors of soap films and oil slicks, the polarization of reflected glare, the continuous spectrum from radio waves to gamma rays, and the interference fringes seen whenever coherent light is split and recombined. The wave description is the foundation of classical optics.

## The sinusoidal plane wave

The simplest useful model is a monochromatic plane wave traveling in the $z$-direction. At position $z$ and time $t$, the electric field amplitude is

$$
	E(z, t) = E_0 \cos(kz - \omega t + \phi_0)
$$

The parameter $E_0$ is the **amplitude**, the peak value of the oscillating field. The **wavenumber** $k = 2\pi / \lambda$ encodes the wavelength $\lambda$, which is the spatial distance between consecutive crests. The **angular frequency** $\omega = 2\pi f$ encodes the frequency $f$, the number of complete oscillations per second at any fixed point in space. The constant $\phi_0$ is an initial **phase offset** that shifts the wave in time or space without changing its shape.

Wavelength and frequency are linked by the wave speed: $\lambda f = c$. Visible light spans wavelengths from roughly $400\text{ nm}$ (violet) to $700\text{ nm}$ (red), corresponding to frequencies of approximately $4.3 \times 10^{14}\text{ Hz}$ to $7.5 \times 10^{14}\text{ Hz}$. Beyond the visible range, the same wave description applies to the entire electromagnetic spectrum — radio waves, microwaves, infrared, ultraviolet, X-rays, and gamma rays differ only in wavelength.

For many purposes, the vector nature of the electromagnetic field can be set aside and light treated as a scalar wave described by the single quantity $E(z,t)$. This scalar approximation is adequate whenever polarization effects are not central, which is the case for most of geometric and physical optics.

## Phase and phase difference

The argument of the cosine, $\Phi(z,t) = kz - \omega t + \phi_0$, is called the **phase**. Phase determines where in its cycle the wave is at a given point and time. Two waves at the same location may have different phases, and this phase difference governs how they combine.

When two waves meet, their superposition depends on their **phase difference** $\Delta\Phi$. If $\Delta\Phi = 0, 2\pi, 4\pi, \ldots$, the waves are in phase and their amplitudes add — this is **constructive interference**, producing a combined wave of greater amplitude. If $\Delta\Phi = \pi, 3\pi, 5\pi, \ldots$, the waves are exactly out of phase and cancel — this is **destructive interference**, producing reduced or zero amplitude. Intermediate phase differences yield intermediate results. This is the principle of superposition applied to sinusoidal waves.

In practice, phase differences most often arise from **path-length differences**. If two waves of the same frequency travel different distances before arriving at the same point, the extra distance $\Delta x$ introduces a phase difference of

$$
	\Delta\Phi = k \cdot \Delta x = \frac{2\pi}{\lambda} \Delta x
$$

This relationship — a path difference of one wavelength corresponds to a phase shift of $2\pi$ — is the central calculation underlying all wave interference phenomena.

## Complex exponential representation

Working directly with cosines becomes algebraically cumbersome when many waves are superposed, because trigonometric identities proliferate. A far more efficient approach uses the complex exponential form, exploiting Euler's formula $e^{i\theta} = \cos\theta + i\sin\theta$. The wave is written as

$$
	E(z, t) = \text{Re}\!\left[E_0 \, e^{i(kz - \omega t + \phi_0)}\right]
$$

Because the wave equation is linear, all algebraic manipulations can be performed on the complex quantity directly, with the real part taken at the end to recover the physical field. It is convenient to factor out the time dependence $e^{-i\omega t}$ (common to all waves of the same frequency) and work with the **complex amplitude**

$$
	\tilde{E} = E_0 \, e^{i\phi_0}
$$

which encodes both the amplitude and the phase in a single complex number.

The physically observable **intensity** — the power per unit area that a detector, photographic film, or the retina actually registers — is proportional to the time-averaged square of the field. In the complex representation this simplifies to

$$
	I \propto |\tilde{E}|^2 = \tilde{E} \, \tilde{E}^*
$$

where $\tilde{E}^*$ is the complex conjugate. When $N$ waves with complex amplitudes $\tilde{E}_1, \tilde{E}_2, \ldots, \tilde{E}_N$ arrive at the same point, the total amplitude is their sum $\tilde{E}_{\text{tot}} = \sum_j \tilde{E}_j$, and the intensity is $I \propto |\tilde{E}_{\text{tot}}|^2$. Expanding this squared magnitude produces cross-terms between every pair of waves — these cross-terms are precisely the interference contributions, positive where phases align (constructive) and negative where they oppose (destructive).

## Spherical waves

A plane wave is an idealization appropriate when the source is very far away — sunlight arriving at Earth, for instance, is well approximated as a plane wave because the Sun is so distant that the curvature of its wavefronts is negligible over any terrestrial scale. A point source at finite distance, by contrast, emits a **spherical wave**. At distance $r$ from the source, the amplitude is

$$
	E(r, t) = \frac{E_0}{r} \cos(kr - \omega t)
$$

The amplitude falls off as $1/r$, and the intensity (proportional to amplitude squared) falls off as $1/r^2$. This inverse-square law for intensity ensures energy conservation: the total power radiated by the source spreads over the surface of an expanding sphere of area $4\pi r^2$, so the power per unit area must decrease as $1/r^2$.

In the complex representation, a spherical wave is written as

$$
	\tilde{E}(r) = \frac{E_0}{r} \, e^{ikr}
$$

omitting the common time factor $e^{-i\omega t}$. The $e^{ikr}/r$ form captures both the $1/r$ amplitude decay and the $kr$ phase accumulation with distance. This expression is the building block for [Huygens' principle](../huygens-principle/), which decomposes an arbitrary wavefront into a collection of such spherical wavelets.

## The wave equation

All of the above solutions are particular solutions of the electromagnetic wave equation. In vacuum, each component of the electric field satisfies

$$
	\nabla^2 E = \frac{1}{c^2} \frac{\partial^2 E}{\partial t^2}
$$

Both the plane wave $e^{i(kz - \omega t)}$ and the spherical wave $e^{ikr}/r$ satisfy this equation (with $\omega = kc$). The linearity of the wave equation is what makes the superposition principle exact: any sum of solutions is also a solution. This linearity is also what makes the complex exponential representation so powerful — the real-part operation commutes with every linear operation, so one can work entirely in the complex domain and take the real part only at the end.

## Significance

The wave model of light is one of the great unifying achievements of nineteenth-century physics. Maxwell's equations predicted electromagnetic waves traveling at the measured speed of light, confirming that light is an electromagnetic phenomenon. The wave model explains interference (as in Young's double-slit experiment and Newton's rings), polarization (as in the darkening of the sky seen through polarizing sunglasses), and the continuous electromagnetic spectrum. It is the prerequisite framework for every wave-optical phenomenon — including, most prominently, diffraction and the resolution limits it imposes on all optical instruments.
