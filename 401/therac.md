# Therac-25


The Therac-25 was a computer-controlled radiation therapy machine produced by Atomic Energy of Canada Limited (AECL) in 1982 after the Therac-6 and Therac-20 units (the earlier units had been produced in partnership with CGR of France).

It was involved in at least six accidents between 1985 and 1987, in which patients were given massive overdoses of radiation.[1]:425 Because of concurrent programming errors, it sometimes gave its patients radiation doses that were hundreds of times greater than normal, resulting in death or serious injury.[2] These accidents highlighted the dangers of software control of safety-critical systems, and they have become a standard case study in health informatics and software engineering. Additionally the overconfidence of the engineers[1]:428 and lack of proper due diligence to resolve reported software bugs are highlighted as an extreme case where the engineers' overconfidence in their initial work and failure to believe the end users' claims caused drastic repercussions.




Problem description

The Therac-25 user interface
The six documented accidents occurred when the high-current electron beam generated in X-ray mode was delivered directly to patients. Two software faults were to blame.[3] One, when the operator incorrectly selected X-ray mode before quickly changing to electron mode, which allowed the electron beam to be set for X-ray mode without the X-ray target being in place. A second fault allowed the electron beam to activate during field-light mode, during which no beam scanner was active or target was in place.

Previous models had hardware interlocks to prevent such faults, but the Therac-25 had removed them, depending instead on software checks for safety.

The high-current electron beam struck the patients with approximately 100 times the intended dose of radiation, and over a narrower area, delivering a potentially lethal dose of beta radiation. The feeling was described by patient Ray Cox as "an intense electric shock", causing him to scream and run out of the treatment room.[4] Several days later, radiation burns appeared, and the patients showed the symptoms of radiation poisoning; in three cases, the injured patients later died as a result of the overdose.[5]