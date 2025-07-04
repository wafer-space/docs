# Packaging Your wafer.space Chips

wafer.space delivers **bare, unpackaged die** by default. This means you receive the raw silicon chips that need to be packaged before they can be easily used in most applications. Understanding your packaging options is crucial for successfully implementing your custom silicon.

## What You Receive from wafer.space

When your wafer.space order is completed, you receive:

- **Bare die** - Individual silicon chips cut from the wafer
- **No packaging** - The chips are not in traditional IC packages (DIP, QFP, BGA, etc.)
- **Wafer map** - Information about which die passed testing (if applicable)
- **Documentation** - Details about pad locations, electrical specifications, and handling requirements

## Packaging Responsibility

:::{important}
**You are responsible for packaging your chips.** wafer.space provides the bare silicon; packaging is a separate step that you must arrange.
:::

However, wafer.space is actively working with packaging partners to provide official turnkey solutions and templates to make this process easier for users.

## Packaging Options Overview

### 1. Chip-on-Board (COB) - Recommended Starting Point

**Best for:** Prototypes, low-volume production, cost-sensitive applications

Chip-on-Board using wire bonding is typically the **easiest, cheapest, and fastest** packaging option for wafer.space users. This approach involves:

- Mounting bare die directly onto a PCB
- Wire bonding the chip pads to PCB traces
- Protecting the assembly with epoxy or glob-top

See our [Chip-on-Board guide](chip-on-board) for detailed information.

### 2. Using Bare Die Directly

**Best for:** Space-constrained applications, specialized test setups

In some cases, you might want to use the bare die without traditional packaging:

- **Die probing** for testing and characterization
- **Direct integration** into specialized assemblies
- **Research applications** where packaging adds unwanted parasitics

See our [Using Bare Die Directly guide](using-bare-die/index) for more information.

### 3. Traditional IC Packaging (Future)

**Best for:** High-volume production, standard applications

wafer.space is working on partnerships to offer traditional packaging options such as:

- **QFN/QFP packages** - Surface-mount packages for standard PCB assembly
- **BGA packages** - High-density ball grid array packages
- **Custom packages** - Specialized packaging for unique requirements

:::{note}
Traditional IC packaging options are under development. Contact wafer.space for current availability and pricing.
:::

## Choosing the Right Packaging Approach

Consider these factors when selecting your packaging strategy:

| Factor | Chip-on-Board | Bare Die Direct | Traditional Packaging |
|--------|---------------|-----------------|----------------------|
| **Cost** | Low | Lowest | High |
| **Speed** | Fast | Fastest | Slow |
| **Volume** | Low-Medium | Very Low | High |
| **Ease of Use** | Moderate | Difficult | Easy |
| **Reliability** | Good | Variable | Excellent |
| **Size** | Compact | Smallest | Standard |

## Getting Started

1. **Review your requirements** - Understand your volume, timeline, and technical needs
2. **Choose an approach** - Start with chip-on-board for most applications
3. **Gather resources** - Review the relevant guides and prepare necessary tools
4. **Plan your PCB design** - Consider packaging requirements early in your PCB layout
5. **Test and iterate** - Start with a small batch to validate your packaging approach

## Section Contents

```{toctree}
---
maxdepth: 2
---
chip-on-board
using-bare-die/index
```

## Need Help?

- Check the [community documentation](../community/index) for user experiences
- Review the [useful resources](../useful-resources) for packaging-related links
- Contact wafer.space for information about packaging partnerships

---

*Packaging is a critical step in bringing your custom silicon to life. Take time to understand your options and choose the approach that best fits your project needs.*