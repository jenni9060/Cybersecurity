# GDPR Compliance Checklist – Web-based Booking System

| **Result** | **Personal data mapping and minimization** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Have all personal data collected and processed in the system been<br> identified? (e.g., name, email, age, username) |
| &nbsp;✅&nbsp; | Have you ensured that only necessary personal data is collected (data minimization)? |
| &nbsp;✅&nbsp; | Is user age recorded to verify that the booker is over 15 years old? |

---

| **Result** | **User registration and management** |
| :----: | :--- |
| &nbsp;❌ pelkkä "I accept the terms of service" -valintaruutu ei ole riittävä GDPR:n mukaisen suostumuksen antamiseen, jos se ei erikseen viittaa henkilötietojen käsittelyyn tai tietosuojakäytäntöön.&nbsp; | Does the registration form (page) include GDPR-compliant consent for processing<br> personal data (e.g., acceptance of the privacy policy)?|
| &nbsp;⚠️ Käyttäjä voi nähdä, mutta ei muokata tai poistaa henkilötietojaan &nbsp; | Can users view, edit, and delete their own personal data via their account? |
| &nbsp;⚠️ On mekanismi, mutta ite Ui:ssa ei ole ainakaan helposti löydettävissä paikkaa mistä admin voisi poistaa käyttäjiä &nbsp; | Is there a mechanism for the administrator to delete a reserver in<br> accordance with the "right to be forgotten"? |
| &nbsp;✅&nbsp; | Is underage registration (under 15 years) and booking functionality restricted? |

---

| **Result** | **Booking visibility** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Are bookings visible to non-logged-in users only at the resource level<br> (without any personal data)? |
| &nbsp;✅&nbsp; | Is it ensured that names, emails, or other personal data of bookers are not exposed<br> publicly or to unauthorized users? |

--- 

| **Result** | **Access control and authorization** |
| :----: | :--- |
| &nbsp;❌ Tällä hetkellä myös reserves voi muokata varauksia. &nbsp; | Have you ensured that only administrators can add, modify, and delete<br> resources and bookings? |
| &nbsp;✅&nbsp; | Is the system using role-based access control (e.g., reserver vs. administrator)? |
| &nbsp;⚠️ Vaikka järjestelmässä on määritetty käyttäjäroolit, ei ole tehty toimia, jotka estäisivät ylläpitäjiä käyttämästä henkilötietoja luvattomiin tarkoituksiin. Toimia voisi olla esim toimintojen lokitus &nbsp; | Are administrator privileges limited to ensure GDPR compliance (e.g., administrators<br> cannot use data for unauthorized purposes)? |

---

| **Result** | **Privacy by Design Principles** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Has Privacy by Default been implemented (e.g., collecting the minimum data by default)? |
| &nbsp;✅&nbsp; | Are logs implemented without unnecessarily storing personal data? |
| &nbsp;✅&nbsp; | Are forms and system components designed with data protection in mind<br> (e.g., secured login, minimal fields)? |

---

| **Result** | **Data security** |
| :----: | :--- |
| &nbsp;⚠️ Osittain. Vielä voisi tarkistaa käyttäjän syötteiden validoinnin kaikkialla, erityisesti lomakkeissa ja URL-parametreissa. Lisäksi voisi käyttää parametrisoituja kyselyitä tai valmisteltuja lauseita SQL-kyselyjen käsittelyssä&nbsp; | Are CSRF, XSS, and SQL injection protections implemented? |
| &nbsp;✅&nbsp; | Are passwords securely hashed using a strong algorithm (e.g., bcrypt, Argon2)? |
| &nbsp;⚠️ En löytänyt varmuuskopiointiin liittyviä asioita&nbsp; | Are data backup and recovery processes GDPR-compliant? |
| &nbsp;⚠️ Tietokanta on paikallinen&nbsp; | Is personal data stored in data centers located within the EU? |

---

| **Result** | **Data anonymization and pseudonymization** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Is personal data anonymized where possible? |
| &nbsp;✅&nbsp; | Are pseudonymization techniques used to protect data while maintaining its utility? |

---

| **Result** | **Data subject rights** |
| :----: | :--- |
| &nbsp;❌ Käyttäjä ei voi ladata tietojaan eikä sovelluksessa ole painiketta tietojen pyytämiselle&nbsp; | Can users download or request all personal data related to them (data access request)? |
| &nbsp;❌&nbsp; | Is there an interface or process for users to request the deletion of their personal data? |
| &nbsp;❌&nbsp; | Can users withdraw their consent for data processing? |

---

| **Result** | **Documentation and communication** |
| :----: | :--- |
| &nbsp;✅&nbsp; | Is there a privacy policy available to users during registration and easily accessible? |
| &nbsp;❌ Tietokantaan oli kirjoitettu hieman dokumentaatiota miksi mitäkin dataa kerätään jne, sinne ei kuitenkaan admin pääse&nbsp; | Are administrators and developers provided with documented data protection practices <br>and processing activities? |
| &nbsp;❌&nbsp; | Is there a documented data breach response process (e.g., how to notify authorities <br>and users of a breach)? |

---

**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)