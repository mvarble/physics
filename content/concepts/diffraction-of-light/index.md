# Diffraction of Light

This document builds on [Wave nature of light](./wave-nature-of-light.md) and [Huygens' principle](./huygens-principle.md).

Diffraction is the departure of light from straight-line propagation when it encounters an obstacle or aperture whose size is comparable to its wavelength. Where geometric optics predicts sharp shadows and well-defined beams, diffraction produces characteristic patterns of bright and dark fringes that spread well beyond the geometric shadow. These patterns are a direct consequence of the wave nature of light, and they impose a fundamental limit on the resolution of every optical system, from the human eye to the largest telescope.

## Experimental setup and regimes

The canonical diffraction experiment consists of a monochromatic plane wave of wavelength $\lambda$ illuminating an aperture cut into an opaque screen, with a second screen at distance $L$ displaying the resulting pattern. The goal is to determine the intensity $I(y)$ at each point on the observation screen.

Two regimes are distinguished by the **Fresnel number** $F = a^2 / (\lambda L)$, where $a$ is the characteristic size of the aperture. When $F \ll 1$, the observation screen is far enough away that the wavelets arriving at any point on it are approximately parallel; this is called **Fraunhofer** or far-field diffraction, and it admits the cleanest analytical results. When $F \gtrsim 1$, the screen is close enough that the curvature of the wavelets matters; this is **Fresnel** or near-field diffraction, and the patterns are more complex though the underlying physics is the same. The discussion here focuses on the Fraunhofer regime, which captures the essential phenomena.

## Single-slit diffraction

Consider a slit of width $a$ extending infinitely in the vertical direction, illuminated by a plane wave of wavelength $\lambda$. The objective is to find the intensity at angle $\theta$ from the straight-ahead direction on a distant screen.

### Setting up the integral

By Huygens' principle, every point across the slit acts as a source of a spherical wavelet. Let $x$ be the coordinate across the slit width, running from $-a/2$ to $a/2$. A wavelet originating at position $x$ must travel an extra distance $x \sin\theta$ to reach a point at angle $\theta$, compared to a wavelet from the center of the slit. The corresponding phase difference is

$$
	\Delta\phi(x) = k \cdot x \sin\theta = \frac{2\pi}{\lambda} x \sin\theta
$$

The total complex amplitude at angle $\theta$ is the integral of all wavelets across the slit:

$$
	\tilde{E}(\theta) \propto \int_{-a/2}^{a/2} e^{i \frac{2\pi}{\lambda} x \sin\theta} \, dx
$$

### Evaluating the integral

Defining $\beta = \frac{\pi a \sin\theta}{\lambda}$, the integral evaluates to

$$
	\tilde{E}(\theta) \propto a \cdot \frac{\sin\beta}{\beta} = a \cdot \text{sinc}(\beta)
$$

where $\text{sinc}(\beta) = \sin\beta / \beta$ is the unnormalized sinc function. The intensity is proportional to the squared magnitude:

$$
	\boxed{I(\theta) = I_0 \left(\frac{\sin\beta}{\beta}\right)^2, \qquad \beta = \frac{\pi a \sin\theta}{\lambda}}
$$

This is the **single-slit diffraction pattern**, one of the central results of wave optics.

### Structure of the pattern

At $\theta = 0$, the parameter $\beta = 0$ and $\lim_{\beta \to 0} (\sin\beta)/\beta = 1$, so $I(0) = I_0$. All wavelets arrive in phase and add constructively, producing the **central maximum** — the brightest feature of the pattern.

The intensity falls to zero when $\sin\beta = 0$ but $\beta \neq 0$, which occurs at $\beta = n\pi$ for integers $n = \pm 1, \pm 2, \ldots$ Substituting back, the **minima** (dark fringes) are located at

$$
	a \sin\theta = n\lambda
$$

The first minimum ($n = 1$) is at $\sin\theta = \lambda / a$, or $\theta \approx \lambda / a$ for small angles. A striking consequence follows immediately: the narrower the slit, the wider the diffraction pattern. Reducing $a$ increases $\theta$, so the light spreads more. This is the opposite of what a particle model would predict — a stream of particles through a narrower opening would produce a narrower, not wider, distribution on the screen. The inverse relationship between slit width and pattern width is a hallmark of wave behavior.

Between the minima lie weaker **secondary maxima**, located approximately where $\tan\beta = \beta$. The solutions are $\beta \approx 1.43\pi,\; 2.46\pi,\; 3.47\pi, \ldots$ The first secondary maximum has intensity only about $4.7\%$ of the central peak, and successive maxima are progressively dimmer. The energy is overwhelmingly concentrated in the central maximum.

### A numerical example

Green light of wavelength $\lambda = 532\text{ nm}$ passing through a slit of width $a = 0.1\text{ mm}$, with an observation screen at $L = 1\text{ m}$, produces a first minimum at $\sin\theta = \lambda / a = 5.32 \times 10^{-3}$, corresponding to $\theta \approx 0.30°$. The displacement on the screen is $y = L\tan\theta \approx 5.3\text{ mm}$ from the center, so the central bright fringe spans about $10.6\text{ mm}$ — over a hundred times wider than the $0.1\text{ mm}$ slit. The Fresnel number is $F = a^2/(\lambda L) \approx 0.019 \ll 1$, confirming the Fraunhofer approximation is appropriate.

## Diffraction by a circular aperture

Most real optical systems — lenses, telescope mirrors, the pupil of the eye — have circular apertures rather than slits. The two-dimensional analog of the single-slit calculation, integrating the Huygens wavelets over a circular disk of diameter $D$, yields the **Airy pattern**:

$$
	I(\theta) = I_0 \left(\frac{2 J_1(x)}{x}\right)^2, \qquad x = \frac{\pi D \sin\theta}{\lambda}
$$

where $J_1$ is the first-order Bessel function of the first kind. The pattern consists of a bright central disk, the **Airy disk**, surrounded by concentric dark and bright rings. The first dark ring occurs at

$$
	\sin\theta \approx 1.22 \frac{\lambda}{D}
$$

This angular radius defines the **Rayleigh criterion** for resolution: two point sources can be distinguished only when their angular separation exceeds $\theta_R = 1.22\lambda / D$. This is the reason larger telescope mirrors yield sharper images, and it establishes a fundamental, inescapable limit on the resolving power of any optical instrument.

As a concrete illustration, the pupil of the human eye in daylight has a diameter of roughly $D \approx 5\text{ mm}$. For green light ($\lambda = 532\text{ nm}$), the Rayleigh criterion gives $\theta_R \approx 1.3 \times 10^{-4}\text{ rad} \approx 0.007°$. At a comfortable reading distance of $25\text{ cm}$, this corresponds to a minimum resolvable feature of about $30\text{ \mu m}$. This is close to the measured acuity limit of human vision — diffraction by the pupil is among the fundamental physical constraints on visual sharpness.

## Diffraction gratings

A diffraction grating consists of many equally spaced parallel slits — typically thousands per millimeter, ruled onto glass or metal. The total pattern is the product of two distinct effects: the single-slit envelope $\text{sinc}^2(\beta)$, which determines the broad shape and overall intensity modulation, and a **multi-slit interference factor** that produces very sharp, narrow bright peaks within that envelope.

For $N$ slits of width $a$ separated by center-to-center distance $d$, the intensity is

$$
	I(\theta) = I_0 \left(\frac{\sin\beta}{\beta}\right)^2 \left(\frac{\sin(N\alpha)}{N\sin\alpha}\right)^2
$$

where $\beta = \frac{\pi a \sin\theta}{\lambda}$ as before and $\alpha = \frac{\pi d \sin\theta}{\lambda}$. The sharp **principal maxima** occur where $\alpha = m\pi$, giving the **grating equation**:

$$
	d \sin\theta = m\lambda \qquad (m = 0, \pm 1, \pm 2, \ldots)
$$

Different wavelengths satisfy this equation at different angles. A grating therefore separates white light into its component wavelengths, producing a spectrum. This is the physics behind the rainbow shimmer visible on the surface of a compact disc, whose closely spaced spiral grooves function as a reflection grating. Gratings are the primary dispersive element in spectrometers used across physics, chemistry, and astronomy.

## Diffraction as a Fourier transform

A deep and powerful connection exists between Fraunhofer diffraction and Fourier analysis. In the far-field limit, the complex amplitude on the observation screen is — up to scaling and overall phase factors — the **two-dimensional Fourier transform** of the aperture function:

$$
	\tilde{E}(k_x, k_y) \propto \iint_{\text{aperture}} A(x, y) \, e^{-i(k_x x + k_y y)} \, dx \, dy
$$

Here $A(x,y)$ equals $1$ inside the aperture and $0$ outside (or more generally, a complex transmission function describing any spatial variation in amplitude or phase across the aperture), and $k_x = k\sin\theta_x$, $k_y = k\sin\theta_y$ are the spatial frequencies corresponding to observation angles. The diffraction pattern is thus the spatial frequency spectrum of the aperture.

This perspective makes the inverse relationship between slit width and pattern width a natural consequence of a general property of Fourier transforms: a function narrow in real space has a broad transform in frequency space, and vice versa. This Fourier duality is analogous to the position–momentum uncertainty relation in quantum mechanics (itself a wave phenomenon). The Fourier optics viewpoint is the standard analytical framework in modern optics, optical information processing, and the design of imaging systems.

## Applications and significance

Diffraction is not merely a textbook curiosity; it pervades both natural phenomena and technology. The Airy pattern sets the fundamental resolution limit for every imaging system: telescopes, microscopes, cameras, lithographic steppers used in semiconductor fabrication, and the eye itself. In spectroscopy, diffraction gratings are the standard tool for dispersing light into its spectrum, enabling chemical analysis, stellar classification, and the measurement of fundamental constants. Laser beams, which pass through finite apertures at every optical element, inevitably diffract and spread; the minimum divergence angle of a Gaussian beam is itself a diffraction effect.

X-ray diffraction exploits the regular atomic lattice of crystals as a three-dimensional grating for X-rays whose wavelength is comparable to atomic spacings. The resulting diffraction patterns reveal molecular structure — this technique produced the famous "Photo 51" that confirmed the double-helix structure of DNA, and it remains the primary method for determining crystal structures in materials science and structural biology. In everyday experience, the rainbow colors on a CD, the starburst halos seen around bright lights through a fine mesh or a fogged window, and the soft fuzzy edges of shadows are all manifestations of diffraction.
