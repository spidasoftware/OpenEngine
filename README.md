OpenEngine
==========

The SPIDACalc Pole Analysis Engine

### Projects

- calc - The main Calc GUI
- min - Integration components for pushing your results to SPIDAMin
- calculations - The analysis engine
- model - The pole and engineering attachment library used
- project - The project model used by calc

### Command Line Tools

The engine can be used from the command line with any JSON [structure](https://github.com/spidasoftware/schema/blob/master/resources/v1/schema/spidacalc/calc/structure.schema) object.  For example:

    gradlew analyze -Pstructure={"structure":"valid pole structure"}
    
This command will output a complete analysis results object conforming to our schema standard found [here](https://github.com/spidasoftware/schema/blob/master/resources/v1/schema/spidamin/asset/standard_details/analysis_asset.schema).

### Visualization Tools

We have included an iterative visualization too to allow for better understanding of how the pole is being solved.

![68747470733a2f2f64726976652e676f6f676c652e636f6d2f75633f6578706f72743d646f776e6c6f61642669643d3042373066323972566c334274566d4a6d644446566148644453334d](https://cloud.githubusercontent.com/assets/482572/2568173/b8c7fc42-b8de-11e3-9a31-83286c03e296.png)

This option should only be enabled during development or debugging because the performance hit is significant.

To enable this option pass the `--visual` option.

