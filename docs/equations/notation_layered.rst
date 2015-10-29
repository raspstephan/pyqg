Layered quasigeostrophic model
==============================

The :math:`{\mathrm{N}}`-layer quasigeostrophic (QG) potential vorticity
is

.. math::

   \begin{aligned}
   {q_1} &= {\nabla^2}\psi_1 + \frac{f_0^2}{H_1} \left(\frac{\psi_{2}-\psi_1}{g'_{1}}\right)\,,  \qquad & i =1{\, ,}\nonumber \\
   {q_n} &= {\nabla^2}\psi_n + \frac{f_0^2}{H_n} \left(\frac{\psi_{n-1}-\psi_n}{g'_{n-1}}  - \frac{\psi_{i}-\psi_{n+1}}{g'_{i}}\right)\,,  \qquad &i = 2,{\mathrm{N}}-1 {\, ,}\nonumber \\
   {q_{\mathrm{N}}} &= {\nabla^2}\psi_{\mathrm{N}}+ \frac{f_0^2}{H_{\mathrm{N}}} \left(\frac{\psi_{\textsf{N}-1}-\psi_{\mathrm{N}}}{g'_{{\mathrm{N}}-1}}\right) + \frac{f_0}{H_{\mathrm{N}}}h_b (x,y)\,,  \qquad & i ={\mathrm{N}}\,,\end{aligned}

where :math:`q_n` is the n’th layer QG potential vorticity, and
:math:`\psi_n` is the streamfunction, :math:`f_0` is the inertial
frequency, n’th :math:`H_n` is the layer depth, and :math:`h_b` is the
bottom topography. (Note that in QG :math:`h_b/H_{\mathrm{N}}<< 1`.)
Also the n’th buoyancy jump (reduced gravity) is

.. math:: g'_n {\ensuremath{\stackrel{\mathrm{def}}{=}}}g \frac{\rho_{n}-\rho_{n+1}}{\rho_n}{\, ,}

where :math:`g` is the acceleration due to gravity and :math:`\rho_n` is
the layer density.

The dynamics of the system is given by the evolution of PV. In
particular, assuming a background flow with background velocity
:math:`\vec{V} = (U,V)` such that

.. math::

   \begin{aligned}
   \label{eq:Udefn}
   u_n^{{{\text{tot}}}} = U_n - \psi_{n y}{\, ,}\nonumber \\
   v_n^{{\text{tot}}} = V_n + \psi_{n x} {\, ,}\end{aligned}

and

.. math:: q_n^{{\text{tot}}} = Q_n + \delta_{n{\mathrm{N}}}\frac{f_0}{H_{\mathrm{N}}}h_b + q_n {\, ,}

where :math:`Q_n + \delta_{n{\mathrm{N}}}\frac{f_0}{H_{\mathrm{N}}}h_b`
is n’th layer background PV, we obtain the evolution equations

.. math::

   \begin{aligned}
   \label{eq:qg_dynamics}
   {q_n}_t + \mathsf{J}(\psi_n,q_n + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_b )& + U_n ({q_n}_x + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_{bx}) + V_n ({q_n}_y + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_{by})+ \nonumber
   \\ & {Q_n}_y {\psi_n}_x - {Q_n}_y {\psi_n}_y = {\text{ssd}}- r_{ek} \delta_{n{\mathrm{N}}} {\nabla^2}\psi_n {\, ,}\qquad n = 1,{\mathrm{N}}{\, ,}\end{aligned}

where :math:`{\text{ssd}}` is stands for small scale dissipation, which
is achieved by an spectral exponential filter or hyperviscosity, and
:math:`r_{ek}` is the linear bottom drag coefficient. The Dirac delta,
:math:`\delta_{nN}`, indicates that the drag is only applied in the
bottom layer.

Equations in spectral space
---------------------------

The evolutionary equation in spectral space is

.. math::

   \begin{aligned}
       \hat{q}_{nt} + (\mathrm{i} k U + \mathrm{i} l V) \left(\hat{q}_n + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}\hat{h}_b\right) + (\mathrm{i} k\, {Q_y} -  - \mathrm{i} l\,{Q_x}){\hat{\psi}_n} + \mathsf{\hat{J}}(\psi_n, q_n + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_b )   \nonumber \\ =  {\text{ssd}}+ \mathrm{i}  \delta_{n {\mathrm{N}}} r_{ek} \kappa^2 \hat{\psi}_n \,, \qquad i = 1,\textsf{N}{\, ,}\end{aligned}

where :math:`\kappa^2 = k^2 + l^2`. Also, in the pseudo-spectral spirit
we write the transform of the nonlinear terms and the non-constant
coefficient linear term as the transform of the products, calculated in
physical space, as opposed to double convolution sums. That is
:math:`\mathsf{\hat{J}}` is the Fourier transform of Jacobian computed
in physical space.

The inversion relationship is

.. math:: \hat{q}_i = {\left({\mathsf{S}}- \kappa^2 {\mathsf{I}}\right)} \hat{\psi}_i{\, ,}

where :math:`{\mathsf{I}}` is the :math:`{\mathrm{N}}\times{\mathrm{N}}`
identity matrix, and the stretching matrix is

.. math::

   \textsf{S} {\ensuremath{\stackrel{\mathrm{def}}{=}}}f_0^2
   \begin{bmatrix}
       -\frac{1}{g'_1 H_1}& & \frac{1}{g'_1 H_1} &  & 0 \dots& \\
    & 0 & & & & &\\
       \vdots & \ddots& &\ddots &\ddots & & & &\\
          & \frac{1}{g'_{i-1} H_i}& &  -\left(\frac{1}{g'_{i-1} H_i} + \frac{1}{g'_{i} H_i}\right)& & \frac{1}{g'_{i} H_i}\,\,\,\,\,\,\, \\
          & \ddots& & \ddots &\ddots & & & &\\
   & & & & & \\
   & \dots & 0 & \frac{1}{ g'_{{\mathrm{N}}-1} H_{\mathrm{N}}}& & -\frac{1}{g'_{{\mathrm{N}}-1} H_{\mathrm{N}}}
   \end{bmatrix}
   {\, .}

Energy spectrum
---------------

The equation for the energy spectrum,

.. math:: E(k,l) {\ensuremath{\stackrel{\mathrm{def}}{=}}}{\frac{1}{2 H}\sum_{i=1}^{{\mathrm{N}}} H_i \kappa^2 |\hat{\psi}_i|^2} \,\,\,\,+ \,\,\,\,\,\, {\frac{1}{2 H} \sum_{i=1}^{{\mathrm{N}}-1} \frac{f_0^2}{g'_i}|\hat{\psi}_{i}- \hat{\psi}_{i+1}|^2}\,\,\,\,,

is

.. math::

   \begin{aligned}
       \frac{d}{dt} E(k,l) = {\frac{1}{H}\sum_{i=1}^{\mathsf{N}} H_i \text{Re}[\hat{\psi}_i^\star {\mathsf{\hat{J}}}(\psi_i,\nabla^2\psi_i)]} +
       {\frac{1}{H}\sum_{i=1}^{\mathsf{N}} H_i\text{Re}[\hat{\psi}_i^\star \hat{\mathsf{J} (\psi_i,({\mathsf{S}}\psi)_i)}]} \nonumber \\
       + {\frac{1}{H}\sum_{i=1}^{\mathsf{N}} H_i ( k U_i +  l V_i)\, \text{Re}[i \, \hat{\psi}^\star_i (\mathsf{S}\hat{\psi}_i)]} \,\,\,\,\,\,\,{- r_{ek} \frac{H_\mathsf{N}}{H} \kappa^2 |\hat{\psi}_{\mathsf{N}}|^2}  +{ {{E_{\text{ssd}}}}} {\, ,}\end{aligned}

where :math:`\star` stands for complex conjugation, and the terms above
on the right represent, from left to right,

I:
    The spectral divergence of the kinetic energy flux;

II:
    The spectral divergence of the potential energy flux;

III:
    The spectrum of the potential energy generation;

IV:
    The spectrum of the energy dissipation by linear bottom drag;

V:
    The spectrum of energy loss due to small scale dissipation.

We assume that :math:`V` is relatively small, and that, in statistical
steady state, the budget above is dominated by I through IV.

Enstrophy spectrum
------------------

Similarly the evolution of the barotropic enstrophy spectrum,

.. math:: Z(k,l) {\ensuremath{\stackrel{\mathrm{def}}{=}}}\frac{1}{2H} \sum_{i=1}^{{\mathrm{N}}} H_i |\hat{q}_i|^2{\, ,}

is governed by

.. math::

   \frac{d}{d t} Z(k,l) = {\text{Re}[\hat{q}_i^\star {\mathsf{\hat{J}}(\psi_i,q_i) ]}}
       {-(k Q_y - l Q_x)\text{Re}[({\mathsf{S}}\hat{\psi}_i^\star)\hat{\psi}_i]}
       + { {\hat{Z_{\text{ssd}}}}}{\, ,}

where the terms above on the right represent, from left to right,

I:
    The spectral divergence of barotropic potential enstrophy flux;

II:
    The spectrum of barotropic potential enstrophy generation;

III:
    The spectrum of barotropic potential enstrophy loss due to small
    scale dissipation.

The enstrophy dissipation is concentrated at the smallest scales
resolved in the model and, in statistical steady state, we expect the
budget above to be dominated by the balance between I and mathrmi.

Vertical modes
--------------

Standard vertical modes, , :math:`{\mathsf{p}}_n (z)`, are the
eigenvectors of the “stretching matrix”

.. math:: {\mathsf{S}}\,{\mathsf{p}}_n = -R_n^{-2}\, {\mathsf{p}}_n\,,

where the :math:`R_n` is the n’th deformation radius.

Linear stability analysis
-------------------------

With :math:`h_b = 0`, the linear eigenproblem is

.. math:: {\mathsf{A}}\, \mathsf{\Phi} = \omega \, {\mathsf{B}}\, \mathsf{\Phi}\,,

where

.. math:: {\mathsf{A}}{\ensuremath{\stackrel{\mathrm{def}}{=}}}\mathsf{B}(\mathsf{U}\, k + \mathsf{V}\,l) + \mathsf{I}\left(k\,\mathsf{Q}_y - l\,\mathsf{Q}_x\right) + \mathsf{I}\,\delta_{\mathsf{N}\mathsf{N}}\, \mathrm{i} \,r_{ek}\,\kappa^2\,,

where :math:`\delta_{\mathsf{N}\mathsf{N}} = [0,0,\dots,0,1]\,,` and

.. math:: \mathsf{B} {\ensuremath{\stackrel{\mathrm{def}}{=}}}\mathsf{S} - \mathsf{I} \kappa^2\,.

The growth rate is Im\ :math:`\{\omega\}`.

Special case: two-layers
========================

With :math:`{\mathrm{N}}= 2`, an alternative notation for the
perturbation of potential vorticities can be written as

.. math::

   \begin{aligned}
       q_1 &= {\nabla^2}\psi_1 + F_1 (\psi_2 - \psi_1) \nonumber\\
       q_2 &= {\nabla^2}\psi_2 + F_2 (\psi_1  - \psi_2){\, ,}\end{aligned}

where we use the following definitions where

.. math:: F_1 {\ensuremath{\stackrel{\mathrm{def}}{=}}}\frac{k_d^2}{1 + \delta^2}\,, \qquad \:\:\text{and} \qquad F_2 {\ensuremath{\stackrel{\mathrm{def}}{=}}}\delta \,F_1\,,

with the deformation wavenumber

.. math:: k_d^2 {\ensuremath{\stackrel{\mathrm{def}}{=}}}\, \frac{f_0^2}{g} \frac{H_1+H_2}{H_1 H_2} {\, .}

With this notation, the “stretching matrix” is simply

.. math::

   {\mathsf{S}}= \begin{bmatrix}
   - F_1 \qquad \:\:\:\:F_1\\
   F_2 \qquad -  + F_2
   \end{bmatrix}{\, .}

The inversion relationship in Fourier space is

.. math::

   \begin{bmatrix}
   \hat{\psi}_1\\
   \hat{\psi}_2\\
   \end{bmatrix}
   = \frac{1}{\text{det} \: {\mathsf{B}}}
   \begin{bmatrix}
   -(\kappa^2 + F_2) \qquad \:\:\:\:-F_1\\
   \:\:\:\: -F_2 \qquad - (\kappa^2 + F_1)
   \end{bmatrix}
   \begin{bmatrix}
   \hat{q}_1\\
   \hat{q}_2\\
   \end{bmatrix}{\, ,}

where

.. math:: \qquad \text{det}\, {\mathsf{B}}= \kappa^2\left(\kappa^2 + F_1 + F_2\right)\,.


Layered quasigeostrophic model
==============================

The :math:`{\mathrm{N}}`-layer quasigeostrophic (QG) potential vorticity
is

.. math::

   \begin{aligned}
   {q_1} &= {\nabla^2}\psi_1 + \frac{f_0^2}{H_1} \left(\frac{\psi_{2}-\psi_1}{g'_{1}}\right)\,,  \qquad & i =1{\, ,}\nonumber \\
   {q_n} &= {\nabla^2}\psi_n + \frac{f_0^2}{H_n} \left(\frac{\psi_{n-1}-\psi_n}{g'_{n-1}}  - \frac{\psi_{i}-\psi_{n+1}}{g'_{i}}\right)\,,  \qquad &i = 2,{\mathrm{N}}-1 {\, ,}\nonumber \\
   {q_{\mathrm{N}}} &= {\nabla^2}\psi_{\mathrm{N}}+ \frac{f_0^2}{H_{\mathrm{N}}} \left(\frac{\psi_{\textsf{N}-1}-\psi_{\mathrm{N}}}{g'_{{\mathrm{N}}-1}}\right) + \frac{f_0}{H_{\mathrm{N}}}h_b (x,y)\,,  \qquad & i ={\mathrm{N}}\,,\end{aligned}

where :math:`q_n` is the n’th layer QG potential vorticity, and
:math:`\psi_n` is the streamfunction, :math:`f_0` is the inertial
frequency, n’th :math:`H_n` is the layer depth, and :math:`h_b` is the
bottom topography. (Note that in QG :math:`h_b/H_{\mathrm{N}}<< 1`.)
Also the n’th buoyancy jump (reduced gravity) is

.. math:: g'_n {\ensuremath{\stackrel{\mathrm{def}}{=}}}g \frac{\rho_{n}-\rho_{n+1}}{\rho_n}{\, ,}

where :math:`g` is the acceleration due to gravity and :math:`\rho_n` is
the layer density.

The dynamics of the system is given by the evolution of PV. In
particular, assuming a background flow with background velocity
:math:`\vec{V} = (U,V)` such that

.. math::

   \begin{aligned}
   \label{eq:Udefn}
   u_n^{{{\text{tot}}}} = U_n - \psi_{n y}{\, ,}\nonumber \\
   v_n^{{\text{tot}}} = V_n + \psi_{n x} {\, ,}\end{aligned}

and

.. math:: q_n^{{\text{tot}}} = Q_n + \delta_{n{\mathrm{N}}}\frac{f_0}{H_{\mathrm{N}}}h_b + q_n {\, ,}

where :math:`Q_n + \delta_{n{\mathrm{N}}}\frac{f_0}{H_{\mathrm{N}}}h_b`
is n’th layer background PV, we obtain the evolution equations

.. math::

   \begin{aligned}
   \label{eq:qg_dynamics}
   {q_n}_t + \mathsf{J}(\psi_n,q_n + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_b )& + U_n ({q_n}_x + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_{bx}) + V_n ({q_n}_y + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_{by})+ \nonumber
   \\ & {Q_n}_y {\psi_n}_x - {Q_n}_y {\psi_n}_y = {\text{ssd}}- r_{ek} \delta_{n{\mathrm{N}}} {\nabla^2}\psi_n {\, ,}\qquad n = 1,{\mathrm{N}}{\, ,}\end{aligned}

where :math:`{\text{ssd}}` is stands for small scale dissipation, which
is achieved by an spectral exponential filter or hyperviscosity, and
:math:`r_{ek}` is the linear bottom drag coefficient. The Dirac delta,
:math:`\delta_{nN}`, indicates that the drag is only applied in the
bottom layer.

Equations in spectral space
---------------------------

The evolutionary equation in spectral space is

.. math::

   \begin{aligned}
       \hat{q}_{nt} + (\mathrm{i} k U + \mathrm{i} l V) \left(\hat{q}_n + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}\hat{h}_b\right) + (\mathrm{i} k\, {Q_y} -  - \mathrm{i} l\,{Q_x}){\hat{\psi}_n} + \mathsf{\hat{J}}(\psi_n, q_n + \delta_{n {\mathrm{N}}} \frac{f_0}{H_{\mathrm{N}}}h_b )   \nonumber \\ =  {\text{ssd}}+ \mathrm{i}  \delta_{n {\mathrm{N}}} r_{ek} \kappa^2 \hat{\psi}_n \,, \qquad i = 1,\textsf{N}{\, ,}\end{aligned}

where :math:`\kappa^2 = k^2 + l^2`. Also, in the pseudo-spectral spirit
we write the transform of the nonlinear terms and the non-constant
coefficient linear term as the transform of the products, calculated in
physical space, as opposed to double convolution sums. That is
:math:`\mathsf{\hat{J}}` is the Fourier transform of Jacobian computed
in physical space.

The inversion relationship is

.. math:: \hat{q}_i = {\left({\mathsf{S}}- \kappa^2 {\mathsf{I}}\right)} \hat{\psi}_i{\, ,}

where :math:`{\mathsf{I}}` is the :math:`{\mathrm{N}}\times{\mathrm{N}}`
identity matrix, and the stretching matrix is

.. math::

   \textsf{S} {\ensuremath{\stackrel{\mathrm{def}}{=}}}f_0^2
   \begin{bmatrix}
       -\frac{1}{g'_1 H_1}& & \frac{1}{g'_1 H_1} &  & 0 \dots& \\
    & 0 & & & & &\\
       \vdots & \ddots& &\ddots &\ddots & & & &\\
          & \frac{1}{g'_{i-1} H_i}& &  -\left(\frac{1}{g'_{i-1} H_i} + \frac{1}{g'_{i} H_i}\right)& & \frac{1}{g'_{i} H_i}\,\,\,\,\,\,\, \\
          & \ddots& & \ddots &\ddots & & & &\\
   & & & & & \\
   & \dots & 0 & \frac{1}{ g'_{{\mathrm{N}}-1} H_{\mathrm{N}}}& & -\frac{1}{g'_{{\mathrm{N}}-1} H_{\mathrm{N}}}
   \end{bmatrix}
   {\, .}

Energy spectrum
---------------

The equation for the energy spectrum,

.. math:: E(k,l) {\ensuremath{\stackrel{\mathrm{def}}{=}}}{\frac{1}{2 H}\sum_{i=1}^{{\mathrm{N}}} H_i \kappa^2 |\hat{\psi}_i|^2} \,\,\,\,+ \,\,\,\,\,\, {\frac{1}{2 H} \sum_{i=1}^{{\mathrm{N}}-1} \frac{f_0^2}{g'_i}|\hat{\psi}_{i}- \hat{\psi}_{i+1}|^2}\,\,\,\,,

is

.. math::

   \begin{aligned}
       \frac{d}{dt} E(k,l) = {\frac{1}{H}\sum_{i=1}^{\mathsf{N}} H_i \text{Re}[\hat{\psi}_i^\star {\mathsf{\hat{J}}}(\psi_i,\nabla^2\psi_i)]} +
       {\frac{1}{H}\sum_{i=1}^{\mathsf{N}} H_i\text{Re}[\hat{\psi}_i^\star \hat{\mathsf{J} (\psi_i,({\mathsf{S}}\psi)_i)}]} \nonumber \\
       + {\frac{1}{H}\sum_{i=1}^{\mathsf{N}} H_i ( k U_i +  l V_i)\, \text{Re}[i \, \hat{\psi}^\star_i (\mathsf{S}\hat{\psi}_i)]} \,\,\,\,\,\,\,{- r_{ek} \frac{H_\mathsf{N}}{H} \kappa^2 |\hat{\psi}_{\mathsf{N}}|^2}  +{ {{E_{\text{ssd}}}}} {\, ,}\end{aligned}

where :math:`\star` stands for complex conjugation, and the terms above
on the right represent, from left to right,

I:
    The spectral divergence of the kinetic energy flux;

II:
    The spectral divergence of the potential energy flux;

III:
    The spectrum of the potential energy generation;

IV:
    The spectrum of the energy dissipation by linear bottom drag;

V:
    The spectrum of energy loss due to small scale dissipation.

We assume that :math:`V` is relatively small, and that, in statistical
steady state, the budget above is dominated by I through IV.

Enstrophy spectrum
------------------

Similarly the evolution of the barotropic enstrophy spectrum,

.. math:: Z(k,l) {\ensuremath{\stackrel{\mathrm{def}}{=}}}\frac{1}{2H} \sum_{i=1}^{{\mathrm{N}}} H_i |\hat{q}_i|^2{\, ,}

is governed by

.. math::

   \frac{d}{d t} Z(k,l) = {\text{Re}[\hat{q}_i^\star {\mathsf{\hat{J}}(\psi_i,q_i) ]}}
       {-(k Q_y - l Q_x)\text{Re}[({\mathsf{S}}\hat{\psi}_i^\star)\hat{\psi}_i]}
       + { {\hat{Z_{\text{ssd}}}}}{\, ,}

where the terms above on the right represent, from left to right,

I:
    The spectral divergence of barotropic potential enstrophy flux;

II:
    The spectrum of barotropic potential enstrophy generation;

III:
    The spectrum of barotropic potential enstrophy loss due to small
    scale dissipation.

The enstrophy dissipation is concentrated at the smallest scales
resolved in the model and, in statistical steady state, we expect the
budget above to be dominated by the balance between I and mathrmi.

Vertical modes
--------------

Standard vertical modes, , :math:`{\mathsf{p}}_n (z)`, are the
eigenvectors of the “stretching matrix”

.. math:: {\mathsf{S}}\,{\mathsf{p}}_n = -R_n^{-2}\, {\mathsf{p}}_n\,,

where the :math:`R_n` is the n’th deformation radius.

Linear stability analysis
-------------------------

With :math:`h_b = 0`, the linear eigenproblem is

.. math:: {\mathsf{A}}\, \mathsf{\Phi} = \omega \, {\mathsf{B}}\, \mathsf{\Phi}\,,

where

.. math:: {\mathsf{A}}{\ensuremath{\stackrel{\mathrm{def}}{=}}}\mathsf{B}(\mathsf{U}\, k + \mathsf{V}\,l) + \mathsf{I}\left(k\,\mathsf{Q}_y - l\,\mathsf{Q}_x\right) + \mathsf{I}\,\delta_{\mathsf{N}\mathsf{N}}\, \mathrm{i} \,r_{ek}\,\kappa^2\,,

where :math:`\delta_{\mathsf{N}\mathsf{N}} = [0,0,\dots,0,1]\,,` and

.. math:: \mathsf{B} {\ensuremath{\stackrel{\mathrm{def}}{=}}}\mathsf{S} - \mathsf{I} \kappa^2\,.

The growth rate is Im\ :math:`\{\omega\}`.

Special case: two-layer model
=============================

With :math:`{\mathrm{N}}= 2`, an alternative notation for the
perturbation of potential vorticities can be written as

.. math::

   \begin{aligned}
       q_1 &= {\nabla^2}\psi_1 + F_1 (\psi_2 - \psi_1) \nonumber\\
       q_2 &= {\nabla^2}\psi_2 + F_2 (\psi_1  - \psi_2){\, ,}\end{aligned}

where we use the following definitions where

.. math:: F_1 {\ensuremath{\stackrel{\mathrm{def}}{=}}}\frac{k_d^2}{1 + \delta^2}\,, \qquad \:\:\text{and} \qquad F_2 {\ensuremath{\stackrel{\mathrm{def}}{=}}}\delta \,F_1\,,

with the deformation wavenumber

.. math:: k_d^2 {\ensuremath{\stackrel{\mathrm{def}}{=}}}\, \frac{f_0^2}{g} \frac{H_1+H_2}{H_1 H_2} {\, .}

With this notation, the “stretching matrix” is simply

.. math::

   {\mathsf{S}}= \begin{bmatrix}
   - F_1 \qquad \:\:\:\:F_1\\
   F_2 \qquad -  + F_2
   \end{bmatrix}{\, .}

The inversion relationship in Fourier space is

.. math::

   \begin{bmatrix}
   \hat{\psi}_1\\
   \hat{\psi}_2\\
   \end{bmatrix}
   = \frac{1}{\text{det} \: {\mathsf{B}}}
   \begin{bmatrix}
   -(\kappa^2 + F_2) \qquad \:\:\:\:-F_1\\
   \:\:\:\: -F_2 \qquad - (\kappa^2 + F_1)
   \end{bmatrix}
   \begin{bmatrix}
   \hat{q}_1\\
   \hat{q}_2\\
   \end{bmatrix}{\, ,}

where

.. math:: \qquad \text{det}\, {\mathsf{B}}= \kappa^2\left(\kappa^2 + F_1 + F_2\right)\,.

