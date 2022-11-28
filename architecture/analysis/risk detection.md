#architecture #analysis #web #risk

> a combination of the consequences that would follow from the occurence of an unwanted event and the likelihood of the occurence of the event

Vulnearibilities are listed here and rated with [[CVSS]]: 
- https://cve.mitre.org/ or newly https://cve.org
- https://nvd.nist.gov/

#### Step 1: Identify Risk
- collect information on:
	- triggers of the threat
	- attack used
	- weakness of the application

#### Step 2: Probability Estimation
- probabilities range between 0 and 9
- trigger of the threat
	- skill level
	- motivation / motives
	- opportunities and resources
	- groupsize of the attackers
- application vulnerability
	- how easy is it to discover?
	- how easy to exploit?
	- what is the vulnearbilitiy's degree of prominence
	- how to detect/recognize an attack?

#### Step 3: Impact Assessment
- technical factors
	- disclosure of sensitive data
	- data corruption
	- service [[availability]]
	- [[traceability]] of the attackers
- business factors
	- financial loss/damage
	- damage to reputation
	- non-compliance
	- data breach

#### Step 4: Risk Weighting
![](risk-weighting.png)
![](risk-weighting2.png)
![](risk-weighting3.png)

#### Step 5: Prioritze Risks
- outcomes
	- prioritized list of risks
- critical risks should be addressed first
- but: not all risks have to be eliminated
- some risks are acceptable

#### Step 6: Adapt Risk Assessment Model
- add new factors
	- new factors that are better tailered to the organization
- customize options
- weight factors