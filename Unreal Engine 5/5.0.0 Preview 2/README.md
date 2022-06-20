This patch file is only for Unreal Engine 5.0.X pulled from the **EpicGames/UnrealEngine** repository on the **release** branch. It is not guaranteed to work with the **ue5-main** branch and likely will not. Once 5.1 comes out I will be porting this over to strata.  

Version: **0.4.1**

This version includes two major changes:

The **Default Lit** shading model now supports retroreflections.
The **Retroreflective** shading model is deprecated and will be removed next version. It does not currently work properly so use **Default Lit** instead.

I am integrating the retroreflective bits into default lit.

Future versions will include integrations into the cloth and eye shading models.


Changes:

Updated to support Unreal Engine 5.0 Preview 2

Fixed issue of material turning black if roughness value was above 0.99

Fixed cooking crash when using the custom retroreflective shading model

Integrated retroreflections into default lit shading model

Deprecated retroreflective shading model

Changed retroreflective specular reflectance model to GTR (Generalized Trowbridge-Reitz) as opposed to GGX (generalized anisotropic GGX)

Changed retroreflective specular reflectance fresnel model to Schlick-Gaussian (spherical guassian term)

Added bool and switch to default lit to enable/disable the retroreflection specular terms if the retroreflection mask input == 0

Added depth fade to the retroreflection specular term (set in ShadingModelsMaterial.ush)

