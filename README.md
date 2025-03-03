## <div align="center"><b>Standards for XRD Data Acquisition & Reporting in MIT AMLS Publications</b></div>
<div align="center">by Tonio Buonassisi (MIT, buonassi@mit.edu) and Jordan Cox (Characterization.nano, jmcox@mit.edu), with input from Kangyu Ji & Fang Sheng. Grateful for technical support from Alexander E. Siemenn. Thanks to Kevin Tran for sharing advice and feedback.</div>
<div align="center">Last updated March 2, 2025</div>

<br><br>

**I. Why I wrote this Document:**

Our lab aims to improve existing materials and discover novel materials
for sustainability, faster than the status quo by combining automation,
machine learning, simulation, and human domain expertise. For example,
one of our research projects might use AI/ML to predict a new material,
then robotics to synthesize materials in the lab to confirm the
prediction. Some of our experimental campaigns produce dozens to
thousands of samples per hour — a very large number to test using
traditional XRD.

**The purpose of this document, is to guide researchers who aim to use
XRD as evidence supporting phase identification of synthesized
samples.** Our group does not always have a trained crystallographer on
board our team, but it does have access to XRD experts at shared-use
facilities who can help with sample prep, measurement, and data
post-processing. Hence, we should have the humility to admit that it is
wise to collaborate with external experts (_e.g_., at
Characterization.nano and other shared-use labs) to make sure we're
performing proper sample-prep, measurements, refinements, and reporting.
On 7/31/24, three AMLS team members (Kangyu, Fang, and Tonio) had a
discussion with Jordan Cox from Characterization.nano, about XRD
standards for their upcoming manuscript. From that discussion, Tonio has
proposed a set of lab-wide standards for XRD data reporting in
publications (journal articles, conference proceedings, posters,
theses...). These standards should enable researchers to progress
quickly toward publication, while including all necessary information to
pass the highest standards of scientific peer review.

<br><br>

**II. Overview of XRD and Fitting Methods**

There are only three pieces of information one can extract information
from in an XRD:

-   Intensities (to first order: electron density inside the unit cell,
    preferred orientation)

-   Peak positions (to first order: lattice parameters, lattice
    symmetry, XRD tool calibration; to second order: strain)

-   Widths (to first order: crystallite size; to second order: strain)

If you had two identical crystals and lattice parameters (point groups)
but two different sets of atoms, one would have the same peak positions
but different peak intensities.

**Gold standard: Rietveld refinement:** When you do a Rietveld
refinement, you're building up a model for what the crystal structure
should have been to produce that diffraction pattern and using that
model to simulate a hypothetical diffraction pattern. Then, you're
testing your structure hypothesis by changing model parameters to
improve the goodness of fit between the simulated pattern and the data.
Every feature of the diffraction pattern is part of the model —
intensities, peak positions, and widths. That's why it's the gold
standard. It does come with some assumptions and constraints — the
biggest constraint is that you must have a crystal structure as a model,
_i.e._, a close-enough hypothesis of the crystal structure. Just like
any fitting method, the closer you are to the right answer, the better
the fitting process converges.

**Silver standard: Pawley, Le Bail, poly fit...**: There are cases when
you don't / can't know what the crystal structure is (_e.g._, a novel
compound), but without atomic coordinates Rietveld refinement cannot be
performed. To determine the structure of an unknown compound, people
first use simplified fitting approaches & models with fewer constraints.
These empirically fit the intensities of the data, rather than simulate
them, shifting each peak up and down individually to improve the fit.
Examples include polynomial fit, Le Bail fit, and Pawley fit. These
require a model for the lattice, but not the atoms. In other words, you
need to propose a unit cell (like a .cif file without atomic
information), and then the model will do its best to adjust unit cell
parameters to get the best fit with the data. With the fitted lattice
parameters and with knowledge of the composition (_e.g_., precursor
ratios, WDS, XRF, EDX...), one _might_ have enough of a guess of the
crystal structure (_i.e._, atomic positions) to attempt Rietveld
refinement again.

**Bronze standard #1: thin film measurements**: In the case of thin-film
measurement, preferred orientation will affect the quality of fit of
Rietveld refinement. The peak intensities will not line up with powder
specimens if preferred orientation is strong. **Therefore, thin-film
samples are inadequate to prove the discovery of a new compound.** One
can shave off the material form the substrate and initiate powder
diffraction measurements, following the two paragraphs above. Or, in
thin-film form, one can superimpose the peak positions on the data,
adjust for strain in the film, and test whether certain known compounds
are consistent with the pattern (although this does not prove unique
fit).

**Bronze standard #2: alloy series**, including in thin-film form: Then,
there are other cases when one doesn't need to make an explicit point
about crystal structure — for example, when scanning a binary series
and showing peaks shifting monotonically from _A_ to _B_. In this case,
showing high-quality (_e.g._, Rietveld) fits for the two end states may
be sufficient for making the scientific argument, that the XRD data
supports the hypothesis of a solid solution in between _A_ and _B_
end-point compositions. In these cases, one might want to also collect
very high-resolution data on individual peaks, and measure their shift.

<br><br>

**III. Gold Standard: Powder XRD + Rietveld Refinement**

<u>When to apply</u>: Whenever possible, and certainly when we
state in our publication that we have "discovered a novel material."

<u>Step 1: Sample prep</u>: Use agate mortar and pestle to grind
the sample. Insert the resulting powder into a microcapillary. Consult
with staff from Characterization.nano with Tonio in cc- regarding choice
of hardware & consumables. Details to be aligned include how to ensure
acceptable particle sizes before packing into a microcapillary (specific
process depends on the material).

<u>Step 2: Powder XRD measurement</u>: Once powder is packed into
a microcapillary, measure in transmission mode.[^1] Ideally, measure
with specimen rotating during measurement.[^2]

<u>Step 3: Report Rietveld Refinement values in the text:</u>
Several values should be reported in the main text, so a
crystallographer can judge whether the Rietveld refinement fit was
properly performed.

-   space group, space group number, and lattice parameters.

-   _R_<sub>exp</sub> tells you about data quality and degree of overfitting. One
    hopes for _R_<sub>exp</sub> around 2--3% or lower. In a sense, this is a
    metric for the quality of the workflow; those wishing to implement a
    "kaizen" mentality can track it over time and see how it improves.

-   _R_<sub>wp</sub> is ideally 10--20%. An explanation is needed if larger

-   _R_<sub>p</sub> is ideally 10--20%. An explanation needed if larger.

-   GOF ideally as close to 1 as possible. Values approaching 2 indicate
    data-quality issues.

<u>Step 4: Plotting data and providing raw data as a supplementary
file:</u>

-   XRD data should show both the individual data points (_e.g._,
    circles) and the Rietveld refinement fit (thin line).

-   Plot the residual and/or <u>normalized residual
    ∆/_σ_ </u>below the XRD pattern. The residual (∆) is the
    data minus the refinement, or observed minus calculated. For the
    normalized residual, ∆ is divided by the standard deviation (_σ_)
    associated with the experimental data at each 2<em>θ</em> value. One should aim for ∆ \<
    15% of max peak height, and ∆/_σ_ values \<\<1 . Achieving these
    depends on the user (you) achieving both <u>high data
    quality</u> (sample prep, measurement acquisition) and
    <u>high fitting quality</u>.

-   How to calculate _σ_: For a single measurement, $σ = \sqrt{I}$, where $I$ is the total XRD detector counts (signal strength) at each 2θ value. For multiple measurements, $σ = \sqrt{I\frac{\sum_{}^{}{(I_{i} - \overline{I})}^{2}}{N - 1}}$, assuming sample does not degrade.

-   Nice-to-have: representation of atomic structure (_e.g_., using
    Crystalmaker)

-   Optional: Plot the peak positions (2<em>θ</em> values) and relative peak
    heights according to the structure file, as narrow lines.

**Example of excellent gold-standard XRD reporting:**

A team led by Schoop and Palgrave wanted to determine if one of the experimental XRD patterns reported in the A-Lab
paper better fit with a simple candidate material (SnO<sub>2</sub>) or a more
complex one (SnSbPb<sub>2</sub>O<sub>6.5</sub>). The team plotted the peak positions for
two candidate structures (blue and red), together with the residual
plotted both in absolute (cyan) and normalized (black) scales, following
the procedure in the previous page. Please take a look at Figure 4 in their paper <http://doi.org/10.1103/PRXEnergy.3.011002>.

<br><br>

**IV. Silver Standard: Pawley refinement for reporting novel compounds**

We can't always meet this gold standard for early-stage materials (e.g.,
novel compounds), because a crystal structure file (with point group and
atomic coordinates & occupancies) does not exist. I'd like to discuss
acceptable and unacceptable practices in this context.

Use case #1 is determining the space group of a novel compound, when you
have a guess about the crystal structure. Pawley refinement (or Le Bail,
or poly fit) fit the intensities of the peaks to determine the structure
factors. (You don't specifically fit the positions or occupancies of
individual atoms — the fits are atom-agnostic.)

Sample prep is the same as Part I.

Several values should be reported in the main text, so a
crystallographer can judge whether the Pawley or Le Bail refinement fit
was properly performed:

-   Any structural parameters that were assumed at the beginning of the
    fit (space group and space-group number).

-   lattice parameters coming from the fit (refinement)

-   _R_<sub>exp</sub> (ideally 2--3% or lower)

-   _R_<sub>wp</sub> (ideally 10--20%; explanation is needed if larger)

-   _R_<sub>p</sub> (ideally 10--20%; explanation needed if larger)

-   Poly or Le Bail fits have slightly better _R_ factors than Rietveld
    (because they're more empirical, less constraints, more degrees of
    freedom)

-   GOF ideally as close to 1 as possible. (values approaching 2
    indicate data-quality issues.)

<u>Plotting data and providing raw data as a supplementary
file:</u>

-   XRD data should show both the individual data points (_e.g_.,
    circles) and the refinement fit (thin line).

-   Plot the <u>residual and/or normalized residual
    ∆/_σ_ </u>below the XRD pattern. The residual (∆) is the
    data minus the refinement, or observed minus calculated. For the
    normalized residual, ∆ is divided by the standard deviation (_σ_)
    associated with the experimental data at each 2<em>θ</em> value. One should aim for ∆ \<
    15% of max peak height, and ∆/_σ_ values \<\<1 . Achieving these
    depends on the user (you) achieving both <u>high data
    quality</u> (sample prep, measurement acquisition) and
    <u>high fitting quality</u>.

-   How to calculate _σ_: For a single measurement, $σ = \sqrt{I}$, where $I$ is the total XRD detector counts (signal strength) at each 2θ value. For multiple measurements, $σ = \sqrt{I\frac{\sum_{}^{}{(I_{i} - \overline{I})}^{2}}{N - 1}}$, assuming sample does not degrade.

-   Nice-to-have: representation of atomic structure (_e.g._, using
    Crystalmaker)

-   Optional: Plot the peak positions (2<em>θ</em> values) and relative peak
    heights according to the assumed structure file after fitting, as
    narrow lines.

**Example of excellent silver-standard XRD reporting:**

<u>Example:</u> In 2016, a team led by Fengxia Wei, Tony Cheetham
and colleagues wanted to figure out if Pb<sup>2+</sup> (in lead-halide
perovskite) could be replaced with a +1 and +3 charged _B_-site cation pair.
They reported the first double perovskite structure, (MA)<sub>2</sub>KBiCl<sub>6</sub>
.[^3] Shijing Sun was a co-author on this paper. During her "Campaign
1.0" in our lab[^4], she discovered Cs<sub>2</sub>AgSbBr<sub>6</sub>, later confirmed in a
follow-up study with Fengxia Wei and Anthony Cheetham.[^5] The overall
development of the field of double perovskites is shared in a nice
perspective.[^6]

Fengxia and colleagues preferred a **Pawley fit**, which refines peak
positions and intensities based solely on lattice parameters (not a
crystallographic model like Rietveld reinfement, which requires atomic
positions / fractional coordinates, atomic displacement parameters,
partial occupancies, bond lengths / angles). See the Supporting Information file of Wei's paper <http://doi.org/10.1039/c9cc01134j>.

<br><br>

**V. Bronze Standard #1: Fitting thin-film samples**

If we make a thin-film sample and want to determine its structure, we
must bear in mind that preferred orientation and strain in the film
compromise our ability to perform Rietveld refinement, so other
strategies are needed. We can shave off the film, grind it into a
powder, and proceed with the Silver or Gold standards above. Or, we can
proceed with a film measurement.

With modest preferred orientation and strain in the film, one can
attempt Rietveld or Pawley/Le Bail/poly fits. Often, this doesn't work.

In those cases, one can perform high-resolution XRD (HRXRD), which is
similar to the other empirical methods and includes a description of the
preferred orientation. Fits can be performed around single peaks or the
entire spectrum, but the HRXRD fit will only apply to the peaks that
have the specified orientation. One can still plot the peak positions
from structure files with the data. This can work for compounds that
might only have a handful of possible structures, and the diffraction
patterns are distinct enough. One example is Robert Hoye's work
discovering methylammonium bismuth iodide. But often, the differences
between spectra are too small, especially when preferred orientation
leads to missing peaks and strain shifts peak positions. One example is
the difficulty distinguishing between the 0D and 2D phases of cesium
bismuth iodide and cesium bismuth bromide.

<br><br>

**VI. Bronze Standard #2: Fitting for compositional gradients**

Let's say we want to estimate the % of _A_ and _B_ in a composition
gradient. We perform XRD on deposited films with strong preferred
orientation (from our high-throughput robotic tool). We have high
confidence in our end compositions.

In this case, we'll want to get good fits for our end compositions _A_
and _B_ — either thin-film form (following the Bronze Standard #1
above) or scraping off the powders (following Gold or Silver Standards).
Then, for the intermediate compositions between _A_ and _B_, taking
high-resolution (in 2<em>θ</em>) measurements around specific peaks, 2<em>θ</em>
ranges, or the entire spectrum is most helpful in measuring small peak
shifts. Peak shifts due to changes in lattice parameters are more
pronounced at higher 2<em>θ</em> angles, hence it's important to collect
data out to high angles, and track the 2<em>θ</em> positions of those peaks
during the compositional gradient _A_ to _B_.

<br><br>

[^1]: In transmission mode, one doesn't need to worry about **irradiated
    volume**, because amount of sample doing the scattering is always
    the same. This contrasts to packing powder into a well and measuring
    in reflectance mode, where the incoming and outgoing X-ray beam
    penetration depth (information depth) may vary depending on material
    density and excitation energy.

[^2]: Rotating the specimen during measurement further reduces the
    chance for preferred orientation to affect the measurement.

[^3]: <https://pubs.rsc.org/en/content/articlelanding/2016/mh/c6mh00053c>
    ; open access: <https://arxiv.org/pdf/1603.00537>

[^4]: <https://doi.org/10.1016/j.joule.2019.05.014>

[^5]: <https://doi.org/10.1039/C9CC01134J>

[^6]: <https://doi.org/10.1039/D4MH90029D>
