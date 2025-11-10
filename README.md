# Income Tax CLI

A small C program that computes income tax for a single person under two regimes:

- OLD regime (with a standard deduction and user-supplied other deductions)
- NEW regime (no deductions assumed)

The program is interactive (CLI) and prints taxable income, tax (including 4% cess), effective tax rate and a recommendation which regime is cheaper.

---

## Files

- `main.c` — C source implementing the tax calculator.
- `tax.exe` — (optional) compiled executable when you build on Windows.

---

## Assumptions

- OLD regime:
  - Standard deduction: ₹50,000 (applied automatically for the OLD regime calculation).
  - You may enter "other deductions" (total) which are subtracted in addition to the standard deduction.
  - Slabs used: 0% up to ₹2,50,000; 5% for ₹2,50,001–₹5,00,000; 20% for ₹5,00,001–₹10,00,000; 30% above ₹10,00,000.

- NEW regime:
  - No standard exemption/deduction is applied.
  - Slabs used: 0% up to ₹2,50,000; 5% for ₹2,50,001–₹5,00,000; 10% for ₹5,00,001–₹7,50,000; 15% for ₹7,50,001–₹10,00,000; 20% for ₹10,00,001–₹12,50,000; 25% for ₹12,50,001–₹15,00,000; 30% above ₹15,00,000.

- A simple rebate (like Section 87A) is modeled so incomes up to ₹5,00,000 may get the tax reduced to zero (up to ₹12,500 reduction).
- Health & Education Cess of 4% is added on the computed tax.
- Surcharge and other complex rules are NOT modeled.
