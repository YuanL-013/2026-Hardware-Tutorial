# HW1 Schematic Self-Check ✅

Feel free to use this checklist as you work through your schematic. 
Tick each box when you have verified it against the homework instructions, template, and relevant datasheets.

> [!TIP]
> **Suggested workflow:** Complete one block → check its connections and values → run ERC/DRC → move to the next block. Run one final check before submitting.

## 🔌 1. Power circuits

- [ ] The 24 V, 5 V, and 3.3 V nets are connected and labelled consistently.
- [ ] The 24 V → 5 V regulator circuit is complete and follows its datasheet.
- [ ] The 5 V → 3.3 V regulator circuit is complete and follows its datasheet.
- [ ] Required input, output, and decoupling capacitors are present with suitable values.
- [ ] Feedback-divider resistor values for ICs are correct where applicable.

<details>
<summary>💡 Quick check: follow the power path</summary>

Trace the circuit from the input connector through the fuse and regulators to each power rail to see if there are smooth transitions between different powers.
</details>

## 🧠 2. MCU and supporting circuits

- [ ] The MCU symbol and every other IC symbol match the intended part and datasheet pinout.
- [ ] Each assigned MCU signal goes to the intended pin and peripheral function.
- [ ] Unused MCU pins are marked as requested in the homework instructions.

<details>
<summary>💡 Quick check: verify by pin number</summary>

Do not rely only on signal names or the visual position of pins on a symbol. Compare pin numbers and functions with the datasheet.

</details>

## 📡 3. Communications and headers

- [ ] Both CAN transceiver circuits are complete, including the components required by their datasheet.
- [ ] MCU transmit and receive signals connect to the appropriate transceiver TXD/RXD pins.
- [ ] CAN connector signals and power pins match the required pinout.


## 🧹 4. Schematic quality

- [ ] Functional blocks are easy to identify and follow.
- [ ] Wires and labels show intentional electrical connections; there are no unintended floating pins or nets.
- [ ] Wires do not obscure or pass through symbols in a confusing way.
- [ ] Bus wires or other grouping methods are used where they improve clarity.
- [ ] All values, references, and net labels remain legible.

## 🚀 5. Before submitting

- [ ] I have checked the schematic against the homework brief and template.
- [ ] I have checked IC pinouts and support circuits against the relevant datasheets.
- [ ] I have run the electrical/design rules check and reviewed all errors and warnings.
- [ ] I have opened the final saved file and confirmed it is the version I intend to submit.
- [ ] The submitted file has a clear name that follows the required naming convention.

> [!IMPORTANT]
> This is a self-check guide, not a substitute for the official homework instructions. If the instructions or a datasheet specify a particular circuit or value, please follow that requirement.
