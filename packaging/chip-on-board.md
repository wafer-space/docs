# Chip-on-Board (Using Wire Bonding)

Chip-on-Board (COB) using wire bonding is often the **easiest, cheapest, and fastest** packaging option for wafer.space users. This approach involves mounting bare die directly onto a PCB and connecting the chip pads to PCB traces using fine wire bonds, then protecting the assembly with encapsulation.

## What is Chip-on-Board?

Chip-on-Board assembly consists of several steps:

1. **Die attach** - Mounting the bare die onto the PCB substrate
2. **Wire bonding** - Connecting chip pads to PCB traces with fine wires
3. **Encapsulation** - Protecting the assembly with epoxy or glob-top
4. **Testing** - Verifying functionality of the completed assembly

This results in a compact, cost-effective package that's well-suited for prototypes and low-to-medium volume production.

## Advantages of COB

### Cost Benefits
- **No package costs** - Eliminates traditional IC packaging expenses
- **Simplified supply chain** - Direct from wafer.space to PCB assembly
- **Lower tooling costs** - No custom package design needed
- **Reduced inventory** - No packaged parts to stock

### Technical Benefits
- **Compact size** - Smaller than equivalent packaged parts
- **Better thermal performance** - Direct thermal path to PCB
- **Reduced parasitics** - Shorter wire bonds than package leads
- **Design flexibility** - Custom pad arrangements possible

### Time Benefits
- **Faster time-to-market** - No packaging lead times
- **Rapid prototyping** - Quick assembly for testing
- **Easy design changes** - Modify PCB without new packages
- **Simplified logistics** - Direct die-to-board flow

## COB Assembly Process

### 1. Die Attach

**Die attach materials:**
- **Conductive epoxy** - For electrical and thermal connection
- **Silver-filled paste** - High thermal and electrical conductivity
- **Eutectic die attach** - For high-reliability applications
- **Thermal interface materials** - For heat-sensitive applications

**Die attach process:**
1. Dispense adhesive onto PCB die attach area
2. Pick and place die using vacuum tooling
3. Align die to PCB reference marks
4. Cure adhesive (typically 150°C for 1-2 hours)

### 2. Wire Bonding

**Wire bonding connects chip pads to PCB traces using:**
- **Gold wire** (most common) - 25μm (1 mil) diameter typical
- **Aluminum wire** - Lower cost, requires different bonding parameters
- **Copper wire** - Emerging technology for high-current applications

**Bonding process:**
1. Program bonder with chip and PCB pad coordinates
2. Position first bond on chip pad
3. Form wire loop to PCB pad
4. Complete second bond on PCB pad
5. Repeat for all connections

### 3. Encapsulation

**Protection methods:**
- **Glob-top epoxy** - Simple, low-cost protection
- **Silicone potting** - Flexible, reworkable protection
- **Rigid encapsulation** - Hard epoxy for harsh environments
- **Conformal coating** - Thin protective layer

## Community Resources and Examples

The open-source community has developed valuable resources for COB assembly:

### Tiny Tapeout COB Work

The Tiny Tapeout project has pioneered accessible COB techniques for the maker community:

**Reference:** [Tiny Tapeout COB Guide](https://www.zerotoasiccourse.com/post/cob/)

This resource provides practical, hands-on guidance for:
- **DIY COB assembly** using readily available equipment
- **PCB design guidelines** optimized for wire bonding
- **Assembly techniques** that work without expensive tooling
- **Troubleshooting tips** from real-world experience
- **Cost optimization** for small volumes

### University of Michigan OpenFASoC Work

The OpenFASoC team at University of Michigan has developed advanced COB implementations:

**Reference:** [OpenFASoC Tapeouts - GF180MCU Padframe](https://github.com/idea-fasoc/openfasoc-tapeouts/tree/main/gf180mcu_padframe)

This repository contains:
- **GF180MCU-specific designs** directly applicable to wafer.space chips
- **Padframe implementations** for COB assembly
- **PCB design files** showing professional COB layouts
- **Assembly documentation** for multi-chip modules
- **Verification approaches** for complex assemblies

Key insights from Mehdi's OpenFASoC work:
- **Systematic padframe design** for reliable wire bonding
- **Multi-die assembly techniques** for complex systems
- **Thermal management strategies** for high-power applications
- **Testing methodologies** for COB assemblies

## PCB Design for COB

### Die Attach Area Design

- **Size the area** to accommodate die plus handling tolerance
- **Include alignment features** like fiducials or hard stops  
- **Plan thermal path** from die to heat spreading areas
- **Consider rework access** if die replacement might be needed

### Wire Bond Pad Design

**Pad specifications:**
- **Minimum size** - 100μm × 100μm for hand bonding, 75μm × 75μm for auto
- **Pad spacing** - Maintain adequate clearance for bond wires
- **Metal finish** - ENIG (gold) preferred for bondability
- **Solder mask** - Open over bond pads, defined openings

**Layout guidelines:**
- **Keep bonds short** - Minimize wire length for better electrical performance
- **Avoid crossing wires** - Plan routing to prevent wire-to-wire contact
- **Group by function** - Place related signals together
- **Include test points** - For post-assembly verification

### Routing Considerations

- **Trace impedance** - Control for high-speed signals
- **Power distribution** - Adequate copper for current requirements
- **Ground planes** - Provide good ground return paths
- **EMI considerations** - Shielding and filtering as needed

## Assembly Equipment Options

### Manual Assembly (Low Volume)

**Basic setup:**
- Stereo microscope (10x-40x magnification)
- Hot plate or small oven for die attach cure
- Manual wire bonder or wedge bonder
- ESD-safe workstation
- Basic dispensing equipment

**Suitable for:**
- Prototypes and development
- Very low volumes (< 100 units)
- Educational purposes
- Proof-of-concept assemblies

### Semi-Automated Assembly (Medium Volume)

**Equipment:**
- Pick-and-place machine for die attachment
- Automatic wire bonder
- Dispensing robot for adhesives
- Convection oven for curing
- Vision system for alignment

**Suitable for:**
- Pre-production builds
- Medium volumes (100-10,000 units)
- Pilot production
- Cost-sensitive applications

### Fully Automated Assembly (High Volume)

**Production line:**
- Automated die attach systems
- High-speed wire bonders
- Inline curing systems
- Automatic encapsulation
- 100% electrical test

**Suitable for:**
- Production volumes (>10,000 units)
- High-reliability applications
- Cost-optimized manufacturing
- Consistent quality requirements

## Quality and Reliability

### Common Issues and Solutions

**Bond failures:**
- **Poor adhesion** - Clean surfaces, proper bonding parameters
- **Wire breaks** - Optimize loop height and wire tension
- **Contamination** - Maintain clean assembly environment

**Die attach problems:**
- **Voids in adhesive** - Proper dispense pattern and cure profile
- **Die tilt** - Ensure flat, clean mounting surface
- **Thermal resistance** - Optimize adhesive thickness and coverage

### Testing and Validation

**Assembly verification:**
- **Continuity testing** - Verify all bonds are intact
- **Functional testing** - Confirm circuit operation
- **Thermal testing** - Validate thermal performance
- **Reliability testing** - Accelerated aging and cycling

## Cost Optimization

### Design for Low-Cost COB

- **Minimize bond count** - Reduce assembly time and cost
- **Standardize processes** - Use common materials and procedures
- **Design for test** - Enable efficient post-assembly verification
- **Plan for yield** - Anticipate and design around common failure modes

### Volume Considerations

| Volume Range | Assembly Approach | Cost per Unit | Setup Cost |
|--------------|------------------|---------------|------------|
| 1-100 | Manual assembly | High | Low |
| 100-1,000 | Semi-automated | Medium | Medium |
| 1,000-10,000 | Automated line | Low | High |
| >10,000 | Optimized production | Lowest | Highest |

## Getting Started with COB

### Step 1: Design Preparation
1. Review the Tiny Tapeout COB guide for basic techniques
2. Study the OpenFASoC padframe designs for professional approaches
3. Design your PCB with COB-friendly features
4. Plan your assembly process and equipment needs

### Step 2: Prototype Assembly
1. Start with manual assembly for first prototypes
2. Use simple glob-top protection initially
3. Focus on functionality before optimizing for production
4. Document your process for repeatability

### Step 3: Scale Considerations
1. Evaluate volume requirements and timelines
2. Consider assembly service providers for higher volumes
3. Plan for quality control and testing
4. Investigate automation options as volumes grow

## Assembly Service Providers

Many PCB assembly houses offer COB services:
- **Local assemblers** - For prototypes and small volumes
- **Specialized COB houses** - For medium to high volumes
- **Turnkey providers** - Full service from PCB to test
- **Academic partnerships** - University fabrication facilities

## Next Steps

Ready to implement COB for your wafer.space chips?

1. **Review the referenced resources** - Study both Tiny Tapeout and OpenFASoC approaches
2. **Design your PCB** with COB requirements in mind
3. **Plan your assembly strategy** based on volume and timeline
4. **Start with prototypes** to validate your approach
5. **Scale gradually** as you gain experience and volume

---

*Chip-on-Board assembly offers an excellent balance of cost, performance, and time-to-market for wafer.space users. Leverage the community's experience to accelerate your own COB success.*