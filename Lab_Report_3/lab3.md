# Lab Report 3: Researching Commands

In this lab report, I will provide some of the command line options for the `grep` command. I will be showing four of them, and for each, I will show their examples, what they do, and what use they're for.

## Recursive (`-r`)
This option make it so that grep will search the keyword in every single line in every file in the given directory. I found this through `grep --help` command and the [Lab 4 task](https://ucsd-cse15l-s23.github.io/week/week4/#counting-sizes-of-text-files).

1. Code example: `grep -r "Kuala Lumpur" stringsearch-data/technical/911report`, which is searching for every lines with instances of `"Kuala Lumpur"` in the entire folder of `911report`. Then, it will print where it's found and the entire line it's at. This is going to be very useful in identifying a keyword (for example, for further investigation) in an entire folder of a lot of text files like the reports of the 9/11 attack without having to check each file one by one. The output is as below.

```
stringsearch-data/technical/911report/chapter-11.txt:                Kuala Lumpur, detailed in chapter 6. In late 1999, the National Security Agency
stringsearch-data/technical/911report/chapter-11.txt:            When the travelers left Kuala Lumpur for Bangkok, local officials were able to
stringsearch-data/technical/911report/chapter-11.txt:                they might have noticed him too. Instead, they were notified only after Kuala Lumpur
stringsearch-data/technical/911report/chapter-11.txt:                bosses that surveillance in Kuala Lumpur was continuing. He may not have known that
stringsearch-data/technical/911report/chapter-13.1.txt:                    traveling to Bangkok and Kuala Lumpur. The NCTC should draw on joint
stringsearch-data/technical/911report/chapter-13.4.txt:                Kuala Lumpur to case U.S. airline flights in the Far East for possible future
stringsearch-data/technical/911report/chapter-13.4.txt:                Sufaat's condominium, an apartment on the outskirts of Kuala Lumpur. Intelligence
stringsearch-data/technical/911report/chapter-13.4.txt:                simply traveled to Kuala Lumpur as Khallad's companion. Intelligence report,
stringsearch-data/technical/911report/chapter-13.4.txt:            60. For Khallad's return to Kuala Lumpur, see Intelligence report, interrogation of
stringsearch-data/technical/911report/chapter-13.4.txt:                chapter 8. That was not known at the time. Mihdhar was met at the Kuala Lumpur
stringsearch-data/technical/911report/chapter-13.5.txt:                before the Joint Inquiry, the Kuala Lumpur meeting took on additional significance
stringsearch-data/technical/911report/chapter-13.5.txt:                (who assisted Mihdhar in Kuala Lumpur).
stringsearch-data/technical/911report/chapter-5.txt:                sent al Qaeda operative Issa al Britani to Kuala Lumpur, Malaysia, to learn about
stringsearch-data/technical/911report/chapter-5.txt:                and JI assisted al Qaeda operatives passing through Kuala Lumpur. One important
stringsearch-data/technical/911report/chapter-5.txt:            Training and Deployment to Kuala Lumpur In the fall of 1999, the four operatives
stringsearch-data/technical/911report/chapter-5.txt:            The four trainees traveled to Kuala Lumpur: Khallad, Abu Bara, and Hazmi came from
stringsearch-data/technical/911report/chapter-5.txt:                they had different tasks. Hazmi and Mihdhar were sent to Kuala Lumpur before
stringsearch-data/technical/911report/chapter-5.txt:                Lumpur from Saudi Arabia via Dubai. Khallad and Abu Bara went to Kuala Lumpur to
stringsearch-data/technical/911report/chapter-5.txt:                Kuala Lumpur clinic called Endolite, and Bin Ladin suggested that he use the
stringsearch-data/technical/911report/chapter-5.txt:            According to Khallad, when he and Abu Bara arrived in Kuala Lumpur they contacted
stringsearch-data/technical/911report/chapter-5.txt:            On December 31, Khallad flew from Kuala Lumpur to Bangkok; the next day, he flew to
stringsearch-data/technical/911report/chapter-5.txt:            After completing his casing mission, Khallad returned to Kuala Lumpur. Hazmi arrived
stringsearch-data/technical/911report/chapter-5.txt:                in Kuala Lumpur soon thereafter and may even have stayed briefly with Khallad and
stringsearch-data/technical/911report/chapter-5.txt:            While in Kuala Lumpur, Khallad wanted to go to Singapore to meet Nibras and Fahd al
stringsearch-data/technical/911report/chapter-5.txt:                and left Kuala Lumpur together. Abu Bara did not have a visa permitting him to
stringsearch-data/technical/911report/chapter-6.txt:                members of "an operational cadre" were planning to travel to Kuala Lumpur in early
stringsearch-data/technical/911report/chapter-6.txt:            He was located leaving Yemen and tracked until he arrived in Kuala Lumpur on January
stringsearch-data/technical/911report/chapter-6.txt:                left Kuala Lumpur on a short flight to Bangkok.
stringsearch-data/technical/911report/chapter-6.txt:                Kuala Lumpur, and the information had been passed on to Berger and the NSC staff and
stringsearch-data/technical/911report/chapter-6.txt:                Kuala Lumpur, let alone that their trail had been lost in Bangkok.
stringsearch-data/technical/911report/chapter-6.txt:            Several weeks later, CIA officers in Kuala Lumpur prodded colleagues in Bangkok for
stringsearch-data/technical/911report/chapter-6.txt:                during Khallad's January 2000 trip to Kuala Lumpur and Bangkok.
stringsearch-data/technical/911report/chapter-7.txt:                that chapter we also described how Mihdhar was spotted in Kuala Lumpur early in
stringsearch-data/technical/911report/chapter-7.txt:                later in the year in Kuala Lumpur to discuss the operation in person again. In late
stringsearch-data/technical/911report/chapter-8.txt:            The CIA asked that a Kuala Lumpur surveillance photo of Mihdhar be shown to the joint
stringsearch-data/technical/911report/chapter-8.txt:                Kuala Lumpur meeting were shown to the source. One was a known photograph of
stringsearch-data/technical/911report/chapter-8.txt:                Cole investigators had no knowledge that Khallad had been in Kuala Lumpur with
stringsearch-data/technical/911report/chapter-8.txt:            Spring 2001: Looking Again at Kuala Lumpur
stringsearch-data/technical/911report/chapter-8.txt:                might occur. We will call him "John." Recalling the episode about the Kuala Lumpur
stringsearch-data/technical/911report/chapter-8.txt:                went cold after the Kuala Lumpur meeting in January 2000, the desk officer moved on
stringsearch-data/technical/911report/chapter-8.txt:            "John's" review of the Kuala Lumpur meeting did set off some more sharing of
stringsearch-data/technical/911report/chapter-8.txt:            "John" gave three Kuala Lumpur surveillance pictures to "Jane" to show to the New
stringsearch-data/technical/911report/chapter-8.txt:                the Kuala Lumpur travel might be significant, and she was not told that someone had
stringsearch-data/technical/911report/chapter-8.txt:                unit, to review all the Kuala Lumpur materials one more time. She had been at the
```
2. Code example: `grep -r "haemoglobin" stringsearch-data/technical/biomed`, which is searching for every lines with instances of `"haemoglobin"` in the entire folder of `biomed`. Then, it will print where it's found and the entire line it's at. This is, again, going to be very useful in identifying a keyword (for example, to more easily study) in an entire folder of a lot of text files like the `biomed` folder attack without having to check each file one by one, easily showing where haemoglobin is and which file talks about it. The output is as below.

```
stringsearch-data/technical/biomed/1471-2350-2-8.txt:          mellitus [ 12]. Glycated haemoglobin (HbAlc) was measured
stringsearch-data/technical/biomed/cc1495.txt:        haemoglobin concentration, and oxygen tension and
```

## Count (`-c`)
This option makes grep prints only the amount of times the given keyword is found on the given file. I found this through `grep --help` command.

1. Code example: `grep -c "interest rates" stringsearch-data/technical/government/Media/Weak_economy.txt`, output: `2`. This command finds the amount of times `"interest rates"` is found in the `Weak_economy.txt` file. This command can be useful when you simply only need to know how much of interest rates is discussed without the context of where it's mentioned.

2. Code example: `grep -c "plane" stringsearch-data/technical/911report/chapter-1.txt`, output: `71`. This command finds the amount of times `"plane"` is found in the `chapter-1.txt` file of the `911report` directory. This command can be useful when you only need to know how many times the word `"plane"` is mentioned in the file, as it might be hard to count one by one if all of the instances are printed instead.

## No File Name (`-h`)
This option makes grep prints only the instances of where the keyword is found; this is only useful in conjunction with other options that make grep check through an entire directory like `-r`. I found this through `grep --help` command.

1. Code example: `grep -h -r "Saudi Arabia" stringsearch-data/technical/911report/`. This command prints all of the instances of `"Saudi Arabia"` in the `911report` directory. This command is useful when you're bothered by the amount of texts on screen while trying to look for specifically about Saudi Arabia in the 9/11 attack report documents. The output is as below.
```
                added to already-crowded agendas with countries like Pakistan and Saudi Arabia.
                the Arabian Peninsula, especially Saudi Arabia and Yemen, and the nearby Horn
                Pakistan, Afghanistan, and Saudi Arabia.
            Saudi Arabia
            Saudi Arabia has been a problematic ally in combating Islamic extremism. At the level
                of high policy, Saudi Arabia's leaders cooperated with American diplomatic
                ingrained in Islamic culture that in Saudi Arabia, for example, a department within
                particularly the Wahhabi sect that flourishes in Saudi Arabia.
            The leaders of the United States and the rulers of Saudi Arabia have long had
                mutual recriminations flow. Many Americans see Saudi Arabia as an enemy, not as an
                One Saudi reformer noted to us that the demonization of Saudi Arabia in the U.S.
                the Palestinians, with whom Saudis ardently sympathize. Although Saudi Arabia's
                internal problems quiet. The Kingdom of Saudi Arabia is now locked in mortal combat
            Saudi Arabia is a troubled country. Although regarded as very wealthy, in fact per
                analysis of Saudi Arabia, contending that fundamentally friendly rulers have been
            There are signs that Saudi Arabia's royal family is trying to build a consensus for
            Cooperation with Saudi Arabia against Islamist terrorism is very much in the U.S.
                    confronted, openly. The United States and Saudi Arabia must determine if they
                opinion of the United States. In Saudi Arabia the number was 12 percent. And
            42. Intelligence report, Fatwa to attack U.S. interests in Saudi Arabia and movement
                of explosives to Saudi Arabia, Jan. 8 1997; trial testimony of Fadl, United States
                Simon, Age of Sacred Terror, pp. 132, 242. On the proposed attack in Saudi Arabia,
                see Intelligence report, Fatwa to attack U.S. interests in Saudi Arabia and movement
                of explosives to Saudi Arabia, Jan. 8, 1997; FBI reports of investigation,
                Saudi discovery of an UBL Network in Saudi Arabia," undated (appears to be May
                1998). On the DCI's visits to Saudi Arabia, see Intelligence reports made available
                over the sanctions." Sheehan added that UNSCR 1333 made Saudi Arabia and the UAE
                to return to Saudi Arabia, had been arrested at JFK Airport in late November 1998.
                and, assisted by the local Saudi consulate, had returned to Saudi Arabia. The new
                Saudi Arabia, June 14, 1998; FBI report of investigation, interview of Mohammad
                Taliban's primary supporters: Pakistan, Saudi Arabia, and the United Arab Emirates.
                to Attack US in Saudi Arabia," June 29, 2001.
                employed by the Saudi Arabian Ministry of Islamic Affairs, Religious Endowments and
                both the Saudi Arabian government and the leadership of the mosque attempted to
                PENTTBOMB Subjects to the Government of Saudi Arabia," undated; FBI letterhead
                own and describing themselves as clerks employed by the Saudi Arabian government.
                in Arizona and return to Saudi Arabia, see ibid. (Sept. 29, 1996, entry citing
                trips home to Saudi Arabia, before departing the United States for the last time in
                colleague planned to execute in Saudi Arabia. FBI electronic communication,
                Republic from Saudi Arabia via Germany but was forced to return to Germany because
                July 17, 2002; Saudi Arabian Mabahith briefing (Oct. 17, 2003) (disclosing that two
                across Saudi Arabia, especially among the southern tribes and those of the hijackers
                areas of Saudi Arabia and chose two Saudi brothers from the al Shehri tribe, of
                records. Saudi Arabian Mabahith briefing (Oct. 17, 2003).
                contact with their families about six months before the attacks. Saudi Arabian
                2003. For difficulties traveling to Chechnya, see also Saudi Arabian Mabahith
                prohibited by Saudi authorities from leaving Saudi Arabia. After being assigned to a
            4 and 5. Saeed al Baluchi and Qutaybah al Najdi. Both were sent to Saudi Arabia via
                operative), and was sent to Saudi Arabia by KSM with 9/11 hijacker Ahmad al Haznawi
                after being sent to Saudi Arabia for a U.S. visa, either because he had second
            9. Mushabib al Hamlan. Sent to Saudi Arabia to acquire a U.S. visa, he and his travel
            In December 1999, while still in high school in Saudi Arabia, Hamlan became involved
                before returning to Saudi Arabia, where they should contact hijacker future 9/11
                insisted on calling his family before leaving Saudi Arabia because he had begun to
                report, operative's travel to Saudi Arabia, Aug. 9, 2002.
                Pakistan, and Saudi Arabia, including all the Commission requested. The White House
                out of Saudi Arabia. The long, disjointed document condemned the Saudi monarchy for
                Saudi Arabia, the home of Islam's holiest sites. He spoke of the suffering of the
                countries such as Saudi Arabia, Morocco, and Jordan still survive today. Those in
                wealth, Saudi Arabia competed with Shia Iran to promote its Sunni fundamentalist
                mainly by financiers in Saudi Arabia and the Persian Gulf states. Donations flowed
            The international environment for Bin Ladin's efforts was ideal. Saudi Arabia and the
            While agents of Bin Ladin began to buy property in Sudan in 1990, Bin Ladin himself moved from Afghanistan back to Saudi Arabia. In
                building this Islamic army, he enlisted groups from Saudi Arabia, Egypt, Jordan,
                leaders had decided a year earlier to attack a U.S. target in Saudi Arabia, and had
                complex in Dhahran, Saudi Arabia, that housed U.S. Air Force personnel. Nineteen
                to Saudi Arabia and asked the Saudis to pardon him. U.S. officials became aware of
                asked what would happen to Bin Ladin should he be sent to Saudi Arabia.
                (Saudi Arabia, Pakistan, and the United Arab Emirates were the only countries that
                Ladin and prominent individuals in Saudi Arabia, including especially the Bin Ladin
                responsibility for attacks in Pakistan or Saudi Arabia. Bin Ladin was described as
                    hold. A senior Bin Ladin operative from Saudi Arabia was to visit IG
                    Saudi Arabia to shoot down an Egyptian plane or, if unsuccessful, a US military
                2001, KSM approached Bin Ladin with the idea of recruiting a Saudi Arabian air force
                his native Saudi Arabia and then visiting his home in Yemen. There, he says, the
                Saudi Arabia from Yemen in early 1998 and helped an embassy bombing operative obtain
                Lumpur from Saudi Arabia via Dubai. Khallad and Abu Bara went to Kuala Lumpur to
                destination because its government did not require citizens of Saudi Arabia or other
                (where he acquired a new passport and a U.S. visa), Saudi Arabia, Bahrain, and one
                Pakistan, then on his return to Saudi Arabia his passport, bearing a Pakistani
                countries and particularly in Saudi Arabia.
            Saudi Arabia has long been considered the primary source of al Qaeda funding, but we
                picture of Bin Ladin's finances. A U.S. interagency group traveled to Saudi Arabia
                It was also disseminated among many young men in Saudi Arabia and Yemen, and caused
            Saudi Arabia.
                mosque and an accredited diplomat at the Saudi Arabian consulate from 1996 until
                Saudi Arabia but was refused entry, based on a determination by the State Department
            Mihdhar and Hazmi said they were students from Saudi Arabia who had just arrived in
                and Saudi Arabia, individuals mainly associated with Mohdar Abdullah and the Rabat
                bank in Riyadh, Saudi Arabia. On September 5, Hazmi deposited $1,900 of the
                introduced Hanjour as a "long time friend from Saudi Arabia." Hazmi told his
            Hani Hanjour, from Ta'if, Saudi Arabia, first came to the United States in 1991 to
                to Saudi Arabia. In 1997, he returned to Florida and then, along with two friends,
                Aviation Administration (FAA) in April 1999. He then returned to Saudi Arabia.
            On June 20, Hanjour returned home to Saudi Arabia. He obtained a U.S. student visa on
                scheduled before leaving Saudi Arabia but never attended. Instead, as mentioned
                Saudi Arabia: Satam al Suqami, Wail al Shehri, Waleed al Shehri, Abdul Aziz al
                underdeveloped area of Saudi Arabia, and shared the same tribal affiliation. None
            The three remaining muscle hijackers from Saudi Arabia were Satam al Suqami, Majed
                between the United States and Saudi Arabia, and stresses practical reasons for
                Wahhabi movement in Saudi Arabia. Saeed al Ghamdi and Mohand al Shehri also spent
            KSM sent the muscle hijacker recruits on to Saudi Arabia to obtain U.S. visas. He
            Having acquired U.S. visas in Saudi Arabia, the muscle hijackers returned to
                of cash and traveler's checks purchased in the UAE and Saudi Arabia. Seven muscle
            On July 4, 2001, Mihdhar left Saudi Arabia to return to the United States, arriving
            In October 2000, a senior operative of Hezbollah visited Saudi Arabia to coordinate
                activities there. He also planned to assist individuals in Saudi Arabia in traveling
                operative. Also in November, Salem al Hazmi apparently flew from Saudi Arabia to
                late October, traveled in a group from Saudi Arabia to Beirut and then onward to
                group of individuals traveling from Saudi Arabia during this same time frame, rather
                perhaps Saudi Arabia or India. Clarke relayed these reports to Rice.
                summer threats seemed to be focused on Saudi Arabia, Israel, Bahrain, Kuwait, Yemen,
                the Visa Express program in Saudi Arabia as a security measure, in order to keep
                same day, Saudi Arabia declared its highest level of terror alert. Despite evidence
```

2. Code example: `grep -r -h "red blood cell" stringsearch-data/technical/biomed/`. This command prints all of the instances of `"red blood cell"` in the `biomed` file directory. This command is useful when you're bothered by the amount of texts on screen while trying to study specifically about the red blood cell in the entirety of the `biomed` folder. The output is as below.
```
          30 min in 1% Evans Blue in PBS to quench red blood cell
          to 4-fold differences in COMT activity in red blood cells
        red blood cells and tissues [ 15 17 18 19 21 22 ] . Lower
        red blood cell (RBC) membrane deformability, lower density
        [ 2 ] . Regular red blood cell transfusions extend
          (packed red blood cells; platelets obtained by apheresis
          assumption is valid for red blood cells [ 29 ] . However,
          red blood cell (RBC) or in platelet (PLT) numbers due to
        less often, red blood cells, platelets, and biopsied
          fraction was removed. The red blood cells were washed
          washed red blood cells was extracted with 20 ml of
        plasma cholesterylesters and red blood cells. The
          interface cells, now depleted of red blood cells, were
        line; SRBC = sheep red blood cells; TNF-α = tumor necrosis
          through steel mesh, and red blood cells were lysed using
          After red blood cell lysis, a single cell suspension
          20 min to sediment the red blood cells preferentially.
        3. anemia - transfusion of packed red blood cells
          or more of packed red blood cell transfusion per day for
        red blood cells. Both of these values are well above the
        less than one unit of packed red blood cells for
          separate red blood cells. After incubation, the
```

## Max (`-m [n]`)
This option modifies grep such that it only display the first `n` instances of the keyword given. Again, I found this command through the `grep --help` command.

1. Code example: `grep -m 3 "admission" stringsearch-data/technical/biomed/cc1477.txt`, which prints the first 3 instances of `"admission"` in the `cc1477.txt` file in the `biomed` folder. This is useful for when you only need some examples of the usage of the word, but you don't want it to potentially display way too many to be fit in the terminal. The output is as below.
```
        medical-surgical ICU has 600 admissions a year. The
        record ICU admissions. The present study presents
        information on all consecutive admissions between 1 March
```
2. Code example: `grep -m 1 "alcohol" stringsearch-data/technical/government/Alcohol_Problems/DraftRecom-PDF.txt`, which prints the first instance of `"alcohol"` in the `DraftRecom-PDF.txt` file in the `government/Alcohol_Problems` directory. Again, this is useful for when you only need one example of the usage of the word, but you don't want it to potentially display way too many to be fit in the terminal. The output is as below.
```
address the full spectrum of alcohol problems among ED
```
