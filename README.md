This repository has code for InsectoSilex, a system for carrying out isotopic microseparation of nitrogen, using microfluidics, insect tissue actuators, and laser differential excitation / sensing.

## Laser and sensor design

The target is $^{15}\mathrm{N}_2$, the nitrogen molecule in which both atoms are the rare isotope. Its natural abundance is $1.34 \times 10^{-5}$, about 1 in 75,000. $^{14}\mathrm{N}^{15}\mathrm{N}$ is much more common, about 1 in 137, and the laser has to miss it.

$^{15}\mathrm{N}_2$ has no dipole, so a single infrared laser does not excite it. The vibration is Raman-active. Measured fundamental band origins:

| Species | Origin |
| --- | --- |
| $^{14}\mathrm{N}_2$ | 2329.912 cm$^{-1}$ |
| $^{14}\mathrm{N}^{15}\mathrm{N}$ | 2291.338 cm$^{-1}$ |
| $^{15}\mathrm{N}_2$ | 2252.078 cm$^{-1}$ |

Drive the $^{15}\mathrm{N}_2$ Q branch with two beams whose frequency difference is 2252.078 cm$^{-1}$. Low-$J$ lines sit near 2252.05 cm$^{-1}$. The nearest $^{14}\mathrm{N}_2$ line is about 1.05 cm$^{-1}$ away and the nearest $^{14}\mathrm{N}^{15}\mathrm{N}$ line is about 3–4 cm$^{-1}$ away. The room-temperature Doppler width of this Raman difference is about 0.005 cm$^{-1}$, so the isotopologues are resolved. A hyperfine calculation is not needed to choose the wavelength: $^{15}\mathrm{N}$ has no quadrupole moment, and the closed-shell hyperfine structure is orders of magnitude smaller than that gap.

Odd-$J$ lines are the stronger set. Nuclear-spin weights in $^{15}\mathrm{N}_2$ are 1 for even $J$ and 3 for odd $J$.

### How the location is sensed

Focus both beams to a few-micrometer spot in the nitrogen stream. $^{15}\mathrm{N}_2$ in that spot emits a third color. With a 532 nm pump the Stokes beam is 604.41 nm and the signal is blue light at 475 nm. A camera with a 475 nm bandpass filter looks at the focus. Blue light means $^{15}\mathrm{N}_2$ is in the spot. Move the focus across the channel, or hold it still and convert arrival time to position with the flow speed.

This tags the molecule with 0.279 eV of vibration. It does not break the N≡N bond or pull the molecule sideways. The blue light at natural abundance is very faint, so the camera integrates, or the stream is already somewhat enriched.

### Hardware

| Piece | Choice | Price |
| --- | --- | --- |
| Green laser | Edmund Optics #23-745, 532 nm, 200 mW, single frequency, 0.01 pm linewidth | $10,780 |
| Orange laser | Toptica DL-SHG pro, tuned near 604 nm | Quote only |
| Camera | Thorlabs CC215MU cooled Quantalux sCMOS | $5,718 |
| Filter | Thorlabs FBH475-25, 475 nm bandpass, blocks 532 nm and 604 nm | $194 |

The green laser is specified as $532 \pm 1$ nm, so 604.41 nm is the Stokes wavelength only when the pump is exactly 532.000 nm. The orange laser has to be tuned, with a wavelength meter, until the difference is 2252.078 cm$^{-1}$. A fixed 604 nm laser with a tolerance of a few nanometers will not select $^{15}\mathrm{N}_2$.

Priced items are about $16,700 before the orange laser. Both lasers are Class 3B.
