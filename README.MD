# Powerfit-examples

This repository contains an example for the [PowerFit](https://github.com/haddocking/powerfit/) package.
The output of this example was generated using PowerFit release version 5.0.2.

## Running the example 

First download the repository and install PowerFit:

```shell
# Clone the example repository
git clone 
# Install PowerFit release version 5.0.2
pip install powerfit-em==5.0.2
```

In this example chain C of the GroEL/ES chaperonin system (PDB entry 3zpz) was fitted into the 
corresponding cryo-EM density map of the full complex (EMDB entry 2325 - 8.9 Å resolution) with
a rotational sampling interval of 5 degrees.

In this repository you find the following files:
- `3zpz_C.cif`
- `EMD-2325.map`
- `output.zip`

The following command can be used to generate the output present in `output.zip`:

```shell
# Run the example
powerfit EMD-2325.map 8.9 3zpz_C.cif --angle 5 --directory output --report --delimiter , 
```

Dependent on your system and the amount of CPUs used to run the example, this run might take ~30 minutes

Please refer to the [manual](https://www.bonvinlab.org/powerfit/manual.html#output) for an explanation
of all the files present in `output.zip`

You can visualize the fits by downloading the output files and opening the result page with
`python3 -m http.server -d .` and clicking `report.html`

While Powerfit clearly favors one location based on cross correlation score and sigma difference, 
there is still a major break in sigma difference between the 7 symetric orientations and the 
next best fit (Fit 8).