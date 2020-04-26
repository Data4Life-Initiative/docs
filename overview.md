# Inspiration (The Problem)
The world is under lockdown. IMF estimates that global GDP will contract by close to 7% in 2020 and the risk of being infected is ever-present. The current state of affairs has led to restrictions in people’s movement and the fear of being infected with the virus as well as the new technology used for contact tracing and surveillance, has instilled privacy concerns.

**LACK OF DATA DUE TO PRIVACY CONCERNS HAMPERS EFFECTIVE MEASURES AGAINST THE SPREAD:** To find the most effective way of fighting the pandemic and its adverse effects on society or to understand how to prevent future outbreaks, we need data. This data is to a great extent missing today. Amid a public crisis or emergency, people want to help and can do so by explicitly consenting to contributing e.g. their medical and location data. However, several issues are holding them back. Amongst other things, there is a lack of trust and transparency in the way their data may be used, and no easy way for people to contribute and control their data, through a lack of tooling. The lack of legal clarity around data sharing also needs to be overcome.

**LACK OF RELIABLE SCIENTIFIC EVIDENCE FOR EFFECTIVE PUBLIC HEALTH RECOMMENDATIONS:** To combat the spread of the virus, some countries, have recommended basic protective measures such as washing our hands, self-isolating if signs of symptoms and avoiding contact with immune-compromised people. However, according to some sources, as many as 80% of people who have contracted COVID-19 may not know it as they are symptom free.

**INEFFECTIVE MEASURES BY AUTHORITIES DUE TO THE LACK OF DATA: **During any emergency, a society may become paralyzed due to uncertainty and fear. This will result in far-reaching social and economic consequences beyond the spread of the disease itself. Sub-optimal use of public resources comes from having a lack of accurate data on which to make decisions, for example, instructions on public lockdown, testing and sanitizing. Locking down entire cities and regions and restricting people’s freedom of movement risk leading to follow-on crises.

# What it does (The Solution)
**A MEANS FOR CITIZENS TO CONTRIBUTE THEIR DATA WITHOUT HAVING TO COMPROMISE THEIR PRIVACY:** (privacy by design). With Data4Life people are empowered to decide how their data is collected, shared and used. Data that is shared for the public good is shared anonymously and sharing is based on explicit consents that can be revoked at any time. Data4Life is not only a COVID-19 solution. It is a platform that can be used for any crisis or emergency at local, regional or national level using the power of many to build resilience.

**RISK SCORING AND ALERTS: **The Data4Life solution notifies people if they are at risk of being infected and recommends a course of action without compromising people's privacy and data subject rights according to the GDPR. With this solution we can reduce the number of asymptomatic transmitters who unknowingly (and unwittingly) are spreading the virus and thereby save lives. By contributing data for the public good, public health recommendations can be fine-tuned: for example, by understanding immunity levels, natural or immunized, in the local community or nationally, lock downs can be enforced or lifted. With citizens donating their data for science, researchers can also get a critical mass of data to prevent future pandemics. If the user’s risk parameters change, the system notifies the user to perform the risk analysis again. Example, it could give a higher risk score due to the person having visited an infection hotspot or have been in contact with an infected person.

**HELP AUTHORITIES and GET SOCIETY BACK ON ITS FEET:** With appropriate quality data, authorities can take effective measures, make informed decisions about the optimal use of public resources, for example, planning sanitation efforts, the sourcing of vaccine and staffing at elderly care facilities). Lockdowns can be limited to where it is needed and people can get back to leading a normal life, faster.

# How we built it
On the client side, it supports three kinds of users: 1) Organisation data admins 2) Citizens and 3) Developers.

All Data4Life APIs are exposed as RESTful APIs, that can be accessed via Bearer access tokens. The solution relies on a mobile phone at the beginning, an OTP-based login solution. In future admins can only login via advanced authentication (LoA3).

The platform is built on a concrete, consent-centric architecture supporting privacy by design and compliance with the GDPR. It uses iGrant.io Open APIs and services for this purpose.

Key aspects of the solution also include, algorithms for risk assessment calculations based on various personal data parameters, area risk ranking, historical and current location data analysis, privacy centric contract tracing (using DP-3T protocol) for personal wellness status assessment.

**Risk Assessment** is performed with the following data:

* Age
* Wellness status: is calculated based on a survey. This can be localised for any country.
* Health status: requires the individual to upload a certificate of immunity or certificate of having done tests with results verified from health authorities or test kit manufacturers using a SSI (Self Sovereign Identity) based verification method.
* Current location data: is used to notify the user in case the person visited an identified hotspot recently. It also alerts if he person has been in contact with an infected person.
* Historic location data: used for risk analysis could be manually entered or could be uploaded from google, facebook, telecom operators and any other third parties where an individual might have that data.
* Contact tracing data: We are also integrating the contact tracing SDK created by the DP-3T project (short for Decentralized Privacy-Preserving Proximity Tracing). This contact tracing protocol created by leading academics from all over Europe embraces privacy-by-design and data minimization principles. We have high hopes of this solution becoming a standard across Europe (or at least heavily influencing an eventual standard). When Apple and Google contact tracing APIs are released, we could replace this with those APIs.

# The value of your solution(s) longterm
Data4Life is an interactive platform whereby citizens can share their data for their own and public good, harnessing the power of big data without compromising people’s privacy and securing a more resilient post COVID-19 society that embraces the freedom of movement. The platform is not just for the current corona crisis we are in. The platform could be used for any pandemic, as a health passport for individuals as well as a pandemic and risk management solution for authorities and business to bring life back to normalcy.

# The necessities in order to continue the project
* Need backing from different data sources for validated and reliable data on hotspots so people can use the app. With a local authority as a data processor, we can easily access verified information on infected individuals. We need to align with data owners to get access to APIs and shorten lead times for handling Data Subject Rights.
* Get legal backing and regulatory vetting, again use a community driven approach to improve on what we have built so far. We now have a draft legal paper around the method we have used that need further vetting.
* Need to get a crowd-sourced view among data scientist community to improve our hotspot algorithms, risk analysis etc. based on what we have built so far. The risk analysis algorithm will be fine tuned further adding new parameters as we find them.
* Need to partner with various self test suppliers to include unique codes with the tests that will serve as quality control for self reporting.
* Address the global multi stakeholder engagement gap. For evidence-based innovation (treatments, effective public health recommendations …..) we need coordination among existing public institutions on local, national and international level – data sources and data using entities and consents!

# Accomplishments that we are proud of
Over the past 2.5 years, we have built iGrant.io, a consent mediation and data exchange platform as per the new data regulations emerging worldwide. This formed an important foundation to address privacy- and freedom of movement concerns in this hackathon. By harnessing the power of many we have created a solution where citizens and institutions can combat COVID-19 by working together.

The team is part of the MyData community that advocates a human centric approach to use of personal data in digitalization. The team has been a contributor in defining and founding the MyData operator group.

Managed to float an open source initiative, Data4Life, to bring in privacy centric solution and got a core group of developers to support it

Got a team of legal and regulatory specialists, healthcare consultants, privacy experts and technologists involved. We also got organisations working in this space involved; iGrant.io, MyData Sweden, Aigine etc.

We were a runner up in the HackTheCrisis Hackathon (save lives - digital category) in Sweden (3-6 April 2020) and came out top 10 in the Global Hack two weeks ago.

# What we learned
Need to allow for different data sources for historic data, continuously improve and align the health status algorithm and mechanisms (by following public recommendations in different countries), align identity on-boarding with national solutions etc. We also need to continuously iterate on our risk ranking algorithm based on surveys etc.
