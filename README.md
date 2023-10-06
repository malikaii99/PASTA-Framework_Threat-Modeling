# Process of Attack Simulation and Threat Analysis (PASTA) Threat Modeling Framework
<h1>Description</h1>

In this exercise, I'll engage in applying the Process of Attack Simulation and Threat Analysis (PASTA) threat model framework to assess the safety of a new shopping app before its launch.

Threat modeling plays a vital role in ensuring the security of software development, with security teams often employing these models to proactively identify vulnerabilities, mitigating risks before potential malicious exploitation occurs. PASTA, a widely utilized framework, helps in evaluating the risk associated with new applications.

<h2>Scenario</h2>

Review the scenario below.

You’re part of the growing security team at a company for sneaker enthusiasts and collectors. The business is preparing to launch a mobile app that makes it easy for their customers to buy and sell shoes.

You are performing a threat model of the application using the PASTA framework. You will go through each of the seven stages of the framework to identify security requirements for the new Sneaker Company app.

First, review the following description of why the sneaker company decided to develop this new app:
Description: Our application should seamlessly connect sellers and shoppers. It should be easy for users to sign-up, log in, and manage their accounts. Data privacy is a big concern for us. We want users to feel confident that we’re being responsible with their information.
Buyers should be able to directly message sellers with questions. They should also have the ability to rate sellers to encourage good service. Sales should be clear and quick to process. Users should have several payment options for a smooth checkout process. Proper payment handling is really important because we want to avoid legal issues.

Next, the application development team is involved with the application because they have the most knowledge about the code base and application logic. Your responsibility as a security professional would be to evaluate the application's architecture for security risks.


<h2>Framework Report </h2>

<h3> Business and Security Objectives</h3>

The primary goal of this application revolves around facilitating secure transactions between sellers and buyers, ensuring users' confidence in the security of their information and the efficiency of the payment process. To achieve this, the application is designed to offer users a variety of payment options, streamlining the checkout process. Compliance with the Payment Card Industry Data Security Standard (PCI DSS) is a fundamental aspect of ensuring the secure handling of payment data.


<h3> Technical Scope </h3>

In the realm of technology, the application leverages several critical components:

  - Application Programming Interface (API): APIs are essential for defining how software elements interact with one another. In this context, third-party APIs are harnessed to augment functionality without necessitating the development of features from scratch.
  - Public Key Infrastructure (PKI): PKI serves as an encryption framework to secure online information exchange. The app employs a combination of symmetric (AES) and asymmetric (RSA) encryption algorithms. AES encryption safeguards sensitive data like credit card information, while RSA encryption facilitates secure key exchange between the app and users' devices.
  - SHA-256: This widely used hash function plays a crucial role in protecting sensitive user data, such as passwords and credit card numbers, by producing a 256-bit digest from an input of any length.
  - Structured Query Language (SQL): SQL is utilized as a programming language to create, interact with, and retrieve data from the application's database. It stores information about available sneakers and their respective sellers while also facilitating data access during the purchase process.

Given the paramount objective of safeguarding private information, the evaluation of PKI technologies is a priority. These technologies play a pivotal role in ensuring the secure exchange of data between users, emphasizing the critical need to protect this information.


<h3> Decomposing of application</h3>

 - [Data flow diagram](https://github.com/malikaii99/PASTA-Framework_Threat-Modeling/blob/a7a4b669f0e7b71acbb4be58af0be03b1644162e/PASTA%20Documents.pdf)

<h3> Threat analysis </h3>

Delving deeper into the PASTA threat model framework, it becomes evident that within this comprehensive approach to threat analysis, two specific types of threats stand out as particularly concerning for the application's data handling: Injection and Session Hijacking.

  - Injection Threats encompass a range of attacks that involve the insertion of malicious code or unauthorized commands into the application's input fields. This could include SQL Injection, where an attacker manipulates input data to gain unauthorized access to the database, or even Cross-Site Scripting (XSS), which involves injecting malicious scripts into web pages viewed by other users. The consequences of successful injection attacks can be severe, potentially leading to data breaches, unauthorized access, or the manipulation of critical system functions.
  - Session hijacking, on the other hand, pertains to the unauthorized interception or theft of user session information, such as session tokens or cookies. Attackers may exploit vulnerabilities to gain access to a user's active session, effectively taking control of their account and potentially engaging in malicious activities on their behalf. Session hijacking can result in unauthorized access, data exposure, and a compromised user experience.

Both of these threat categories underscore the critical importance of identifying and addressing vulnerabilities within the application's security framework. Vulnerabilities that remain unmitigated can provide the foothold that malicious actors need to exploit these threats, compromising the confidentiality, integrity, and availability of user data.

To counteract these threats effectively, it is imperative that the application employ robust security measures, such as input validation, output encoding, session management best practices, and continuous monitoring. Additionally, regular security assessments and penetration testing can help uncover and rectify vulnerabilities before they are exploited, ensuring that user data remains secure and the application maintains its integrity.

<h3> Vulnerability analysis </h3>

Moreover, as we delve deeper into the comprehensive analysis provided by the PASTA threat model framework, it becomes evident that two specific vulnerabilities have been identified, signifying potential points of exploitation for malicious actors. These vulnerabilities, namely the "Lack of Prepared Statements" and "Broken API Tokens," serve as poignant reminders of the critical importance of addressing these weaknesses within the application's overarching security strategy.

The vulnerability known as "Lack of Prepared Statements" indicates a gap in the application's protection against SQL injection attacks. When developers fail to implement prepared statements in their database queries, it leaves open a window of opportunity for attackers to manipulate input data in a way that can lead to unauthorized access to the database. This vulnerability, if not promptly rectified, can expose the application to significant risks, including data breaches, unauthorized access, and potential damage to the application's integrity.

Similarly, the "Broken API Tokens" vulnerability raises concerns regarding the application's security posture, particularly in the context of its API usage. A broken API token system can result in the misuse or exploitation of API functionalities, potentially allowing unauthorized access to sensitive data or critical system operations. Addressing this vulnerability is paramount to ensuring the integrity and security of the application's interactions with external services and resources.

In light of these vulnerabilities, it is incumbent upon the application's security team and developers to take proactive measures. These measures may include implementing robust input validation and output encoding to thwart SQL injection attempts and fortifying the API token system to ensure its resilience against exploitation. Furthermore, regular security assessments and penetration testing should be integrated into the development lifecycle to continuously identify and remediate vulnerabilities, thereby enhancing the application's overall security posture.

By acknowledging and diligently addressing these vulnerabilities, the application can fortify its defenses, minimize the risk of exploitation, and ultimately provide a safer and more secure environment for users, ensuring the confidentiality and integrity of their data.


<h3> Attack modeling </h3>

 - [Attack tree](https://github.com/malikaii99/PASTA-Framework_Threat-Modeling/blob/a7a4b669f0e7b71acbb4be58af0be03b1644162e/PASTA%20Documents.pdf)

   
<h3> Risk analysis and impact </h3>

To mitigate these risks and enhance security, the application implements four key security controls that have been learned:

  - SHA-256: Used for data protection.
  - Incident Response Procedures: To effectively respond to security incidents.
  - Password Policy: To enforce strong password practices.
  - Principle of Least Privilege: Restricting user access to only what is necessary.

These security controls collectively contribute to a robust security posture, reinforcing the application's ability to protect sensitive user information and provide a secure environment for transactions.
