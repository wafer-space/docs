# Die Probing

Die probing is a technique for making temporary electrical connections to bare die for testing, characterization, and debugging. This approach is essential for validating your chips before committing to permanent packaging and can be used for production testing of wafer.space die.

## What is Die Probing?

Die probing involves using small, spring-loaded metal tips (probes) to make temporary electrical contact with the bond pads on your die. This allows you to:

- **Test functionality** before packaging
- **Characterize performance** across process variations  
- **Debug design issues** with full signal access
- **Perform burn-in testing** at the die level
- **Sort known good die (KGD)** for packaging

## Probe Tile Approach

One effective approach for wafer.space users is to design **probe tiles** - special test structures that don't require packaging and follow established specifications for easier testing.

### SKY130 Test Tile Reference

The open-source community has developed probe tile specifications that can be adapted for GF180MCU. The original SKY130 test tile specifications provide a foundation:

**Reference:** [SKY130 Test Tile Specs](https://bit.ly/test-open-pdk)

These specifications define:
- **Probe pad layouts** optimized for automatic test equipment
- **Test structure guidelines** for process characterization
- **Electrical specifications** for probe contact
- **Design rules** for reliable probing

### Adapting for GF180MCU

When designing probe tiles for your wafer.space GF180MCU chips:

1. **Probe Pad Design**
   - Use minimum 75μm × 75μm probe pads
   - Provide 100μm pitch for automatic probers
   - Include guard rings around sensitive circuits
   - Follow GF180MCU design rules for metal layers

2. **Test Structures**
   - Include process monitor structures
   - Add parametric test devices (resistors, capacitors, transistors)
   - Design ring oscillators for speed characterization
   - Include ESD protection test structures

3. **Layout Considerations**
   - Place probe pads away from fragile circuit areas
   - Use thick top metal layers for probe contact
   - Provide adequate spacing between probe sites
   - Include alignment marks for automated systems

## Probe Station Setup

### Manual Probe Stations

For low-volume testing and development:

**Basic Requirements:**
- Microscope with adequate magnification (50x-200x)
- XYZ micromanipulators for probe positioning
- Chuck for holding the die or wafer
- ESD protection and shielding
- Test equipment connections

**Typical Workflow:**
1. Mount die on probe station chuck
2. Position probes using micromanipulators
3. Make contact with bond pads or probe pads
4. Perform electrical measurements
5. Record results and move to next die

### Automated Probe Systems

For higher volumes or production testing:

**Advantages:**
- Faster throughput (hundreds of die per hour)
- Better repeatability and accuracy
- Reduced operator fatigue
- Comprehensive data logging
- Integration with test equipment

**Considerations:**
- Higher capital cost
- Requires probe card design
- Setup time for new designs
- Maintenance and calibration needs

## Probe Card Design

For automated testing, you'll need a custom probe card:

### Probe Card Types

1. **Blade Cards** - Simple, low-cost, limited pin count
2. **Vertical Cards** - Higher density, better for fine pitch
3. **MEMS Cards** - Highest density, most expensive
4. **Cantilever Cards** - Good for large die, flexible contact

### Design Considerations

- **Probe tip material** - Tungsten, beryllium copper, or specialized alloys
- **Contact force** - Balance between good contact and pad damage
- **Probe spacing** - Match your pad layout and pitch
- **Electrical design** - Minimize parasitics and crosstalk
- **Thermal management** - Consider heating for some tests

## Testing Strategies

### Functional Testing
- **Digital circuits** - Apply test vectors and verify outputs
- **Analog circuits** - Measure DC and AC characteristics  
- **Mixed-signal** - Test both digital and analog portions
- **Built-in self-test (BIST)** - Use on-chip test circuits

### Parametric Testing
- **Process monitors** - Verify fabrication quality
- **Speed characterization** - Measure critical path delays
- **Power consumption** - Static and dynamic power measurement
- **Temperature characterization** - Performance across temperature

### Reliability Testing
- **Burn-in** - Accelerated aging at elevated temperature
- **ESD testing** - Verify protection circuit effectiveness
- **Latch-up testing** - For CMOS circuits
- **Hot carrier testing** - Long-term reliability assessment

## Design for Probe (DFP)

Design your chips with probing in mind:

### Probe Pad Guidelines
- **Size** - Minimum 50μm × 50μm for manual, 75μm × 75μm for auto
- **Spacing** - Allow room for probe placement without interference
- **Metal stack** - Use top metal layer for probe contact
- **Protection** - Include current limiting for sensitive circuits

### Test Access
- **Bring out internal signals** to probe pads for debugging
- **Include test modes** to enable/disable circuit blocks
- **Add scan chains** for digital logic testing
- **Provide power domains** that can be controlled independently

### Process Monitoring
- **Include test structures** on every die for process verification
- **Add temperature sensors** for thermal characterization
- **Include voltage references** for measurement calibration
- **Design ring oscillators** for speed monitoring

## Probe Contact Issues

Common problems and solutions:

### Poor Contact
- **Symptoms** - High resistance, intermittent connections
- **Causes** - Contaminated pads, insufficient contact force
- **Solutions** - Clean pads, adjust probe force, use better probe tips

### Pad Damage
- **Symptoms** - Scratched or gouged probe pads
- **Causes** - Excessive contact force, hard probe tips
- **Solutions** - Reduce force, use softer probe materials, limit scrub

### Electrical Interference
- **Symptoms** - Noisy measurements, crosstalk
- **Causes** - Poor grounding, inadequate shielding
- **Solutions** - Improve ground connections, add guard traces

## Cost and Time Considerations

### Manual Probing
- **Setup cost** - Moderate (probe station, microscope)
- **Per-die cost** - High labor cost
- **Speed** - Slow (minutes per die)
- **Best for** - Development, low volume, debugging

### Automated Probing
- **Setup cost** - High (prober, probe cards)
- **Per-die cost** - Low once amortized
- **Speed** - Fast (seconds per die)
- **Best for** - Production, high volume, consistent testing

## Getting Started

1. **Design probe-friendly layouts** early in your design process
2. **Include test structures** and probe pads in your tape-out
3. **Start with manual probing** for initial characterization
4. **Consider automated solutions** for higher volumes
5. **Document your probe plan** and share with the community

## Resources

- [SKY130 Test Tile Specifications](https://bit.ly/test-open-pdk) - Reference design guidelines
- Cascade Microtech Probe Station Manuals - Industry standard equipment
- FormFactor Probe Card Design Guides - Professional probe card design
- Academic papers on probe card design and DFP techniques

---

*Die probing is essential for validating your wafer.space chips and ensuring successful packaging. Start with simple manual setups and scale to automated systems as your volumes grow.*