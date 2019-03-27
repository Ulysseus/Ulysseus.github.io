STARKS Polynomial Proofs

I have just got back from DEVCON 3 in Cancun. One particular talk had a huge effect on me, it was a breakaway talk, by Prof Eli Ben-Sassoon. on arithmetization and STARKs. So now that I have had little time, I sat down and in my own simplistic way I tried to understand. My late father used to say you can always spot an idiot, when presented with an abstract mathematical proof, they will start substituting numbers, that is exactly what I will do in this post, sorry Dad but I find that it aids understanding. This post is a simplistic attempt of explaining what this is all about;

Suppose you have a function that is lookup table or program, this function is public. Now you have some private input x_private and a public input x_public
```
f(x_private|x_public) = y.
```
From what I understand a zero knowledge proof (ZKP) is that you want to prove that you know x_private such that F(x_private|x_public) = y. Without leaking any information about x_private.

So think of x_private as a database. x_public is a possible entry in that database and y is True or False. We want to be able to do the computation with Integrity that is if we get an answer y, we can be really sure that it is y. We want it to be private that is it does not leak any informtion about x_private.

Now it would be really nice if we had succinctness. That is a verifier will take less steps to verify the answer, than to do the actual computation of f.

The talk was a presentation of how to achieve these aims using polynomials.

First some basic intuition about polynomials, they are a formal sum of ai x^i of powers of x. The highest non zero term is termed the degree of the polynomial. So basically they are a program for calculating a number, assume that all inputs and coefficients are integers from now on. Consider if you have two points you can always fit a line that will go through both points. A line is polynomial of degree 1. In fact given n points its always possible to find a polynomial of degree n-1 that is guaranteed to pass through those n points. A little bit of thought will show that any two polynomials of degree m, agree on at most m points. Two straight lines which are not equal will intersect at one point or none at all. The nature of polynomials is such that they may agree on a set of points but they can oscillate widely between the points and outside the range of interest. This is what makes them difficult to work with for most numerical problems.

Alright onto the problem:

Bob claims “I have a list with 1 000 000 integers all are between 1 and 10.

Can Alice check this with two queries and 99% certainity?

Naive answer of course is no!

Now Bob says I have encoded the list as 1 000 000 degree polynomial evaluated on 1 000 000 000 points.

Okay so lets do this for real:

Heres a list of 100 random numbers between 1 and 10
```
{9, 6, 1, 6, 10, 2, 4, 6, 3, 2, 2, 9, 4, 7, 4, 9, 10, 6, 2, 6, 10, 8, 3, 9, 1, 9, 2, 3, 10, 4, 5, 9, 7, 2, 9, 6, 6, 9, 8, 3, 2, 10, 10, 9, 2, 7, 3, 8, 10, 2, 8, 6, 4, 8, 4, 2, 3, 6, 7, 3, 7, 9, 6, 5, 1, 2, 6, 4, 6, 8, 4, 4, 4, 8, 1, 4, 2, 9, 9, 9, 3, 10, 10, 10, 5, 10, 5, 8, 2, 3, 4, 3, 5, 10, 8, 2, 2, 5, 8, 10}
```
This is what a 99 degree polynomial that passes through those points looks like
```
-2.06381*10²⁹ + 1.06527*10³⁰ x — 2.58062*10³⁰ x² +3.94243*10³⁰ x³ — 4.29722*10³⁰ x⁴ + 3.58007*10³⁰ x⁵ -2.3827*10³⁰ x⁶ + 1.30659*10³⁰ x⁷ — 6.03972*10²⁹ x⁸ +2.39525*10²⁹ x⁹ — 8.26444*10²⁸ x¹⁰ + 2.50928*10²⁸ x¹¹ -6.76797*10²⁷ x¹² + 1.63456*10²⁷ x¹³ — 3.559*10²⁶ x¹⁴ +7.02736*10²⁵ x¹⁵ — 1.26478*10²⁵ x¹⁶ + 2.08427*10²⁴ x¹⁷ -3.15744*10²³ x¹⁸ + 4.41269*10²² x¹⁹ — 5.70738*10²¹ x²⁰ +6.8514*10²⁰ x²¹ — 7.65338*10¹⁹ x²² + 7.97399*10¹⁸ x²³ -7.76559*10¹⁷ x²⁴ + 7.08263*10¹⁶ x²⁵ — 6.06053*10¹⁵ x²⁶ +4.87339*10¹⁴ x²⁷ — 3.68815*10¹³ x²⁸ + 2.63053*10¹² x²⁹ -1.77046*10¹¹ x³⁰ + 1.12576*10¹⁰ x³¹ — 6.77013*10⁸ x³² +3.85451*10⁷ x³³ — 2.07953*10⁶ x³⁴ + 106403. x³⁵ -5167.42 x³⁶ + 238.365 x³⁷ — 10.4508 x³⁸ + 0.435771 x³⁹ -0.0172907 x⁴⁰ + 0.000653182 x⁴¹ — 0.0000235031 x⁴² +8.05876*10^-7 x⁴³ — 2.63408*10^-8 x⁴⁴ + 8.21014*10^-10 x⁴⁵ -2.44099*10^-11 x⁴⁶ + 6.92444*10^-13 x⁴⁷ — 1.87458*10^-14 x⁴⁸ +4.844*10^-16 x⁴⁹ — 1.19495*10^-17 x⁵⁰ + 2.81442*10^-19 x⁵¹ -6.32929*10^-21 x⁵² + 1.35914*10^-22 x⁵³ — 2.78691*10^-24 x⁵⁴ +5.45648*10^-26 x⁵⁵ — 1.02001*10^-27 x⁵⁶ + 1.82036*10^-29 x⁵⁷ -3.101*10^-31 x⁵⁸ + 5.04154*10^-33 x⁵⁹ — 7.82067*10^-35 x⁶⁰ +1.15725*10^-36 x⁶¹ — 1.63298*10^-38 x⁶² + 2.19658*10^-40 x⁶³ -2.8155*10^-42 x⁶⁴ + 3.4372*10^-44 x⁶⁵ — 3.99462*10^-46 x⁶⁶ +4.41694*10^-48 x⁶⁷ — 4.64376*10^-50 x⁶⁸ + 4.63895*10^-52 x⁶⁹ -4.39984*10^-54 x⁷⁰ + 3.95872*10^-56 x⁷¹ — 3.37575*10^-58 x⁷² +2.72545*10^-60 x⁷³ — 2.08098*10^-62 x⁷⁴ + 1.5008*10^-64 x⁷⁵ -1.02095*10^-66 x⁷⁶ + 6.5413*10^-69 x⁷⁷ — 3.94067*10^-71 x⁷⁸ +2.22803*10^-73 x⁷⁹ — 1.17984*10^-75 x⁸⁰ + 5.83815*10^-78 x⁸¹ -2.69255*10^-80 x⁸² + 1.15406*10^-82 x⁸³ — 4.58194*10^-85 x⁸⁴ +1.67883*10^-87 x⁸⁵ — 5.65258*10^-90 x⁸⁶ + 1.7403*10^-92 x⁸⁷ -4.87123*10^-95 x⁸⁸ + 1.23122*10^-97 x⁸⁹ — 2.78733*10^-100 x⁹⁰ +5.59628*10^-103 x⁹¹ — 9.84338*10^-106 x⁹² + 1.49331*10^-108 x⁹³ -1.9144*10^-111 x⁹⁴ + 2.0166*10^-114 x⁹⁵ — 1.67589*10^-117 x⁹⁶ +1.03026*10^-120 x⁹⁷ — 4.16516*10^-124 x⁹⁸ + 8.30655*10^-128 x⁹⁹
```
Notice that the coefficients are actually integers or ratios of integers but its difficult to format such large numbers on medium so I have approximated them with floating point numbers (Don’t do this if you are trying to implement this stuff)

Lets call this polynomial f.
```
f(5) = 10; f(1) =9 as expected and of course theres nothing preventing us from calculating

f(201)=4227931031356271700110404435764961826803213492721343072590406053959243356640246734003894
```
Okay so before we continue we need two more polynomials

Firstly we need a constraint polynomial c(x)
```
c = (1 — x) (2 — x) (3 — x) (4 — x) (5 — x) (6 — x) (7 — x) (8 -x) (9 — x) (10-x)
```
If you plug 1,2…10 into c(x) you can see that its zero for any of these values. Because its a product of ten terms its a degree 10 polynomial.

Now lets define a polynomial of degree 100
```
d(x) = (100 -x) (99 -x) (98 -x) (97 -x) (96 -x) (95 -x) (94 -x) (93 -x) (92 -x) (91 -x) (90 -x) (89 -x) (88 -x) (87 -x) (86 -x) (85 -x) (84 -x) (83 -x) (82 -x) (81 -x) (80 -x) (79 -x) (78 -x) (77 -x) (76 -x) (75 -x) (74 -x) (73 -x) (72 -x) (71 -x) (70 -x) (69 -x) (68-x) (67 -x) (66 -x) (65 -x) (64 -x) (63 -x) (62 -x) (61 -x) (60 -x) (59 -x) (58 -x) (57 -x) (56- x) (55 -x) (54 -x) (53 -x) (52 -x) (51 -x) (50 -x) (49 -x) (48 -x) (47 -x) (46 -x) (45 -x) (44 -x) (43 -x) (42 -x) (41 -x) (40 -x) (39 -x) (38 -x) (37 -x) (36 -x) (35 -x) (34 -x) (33 -x) (32-x) (31 -x) (30 -x) (29 -x) (28 -x) (27 -x) (26 -x) (25 -x) (24 -x) (23 -x) (22 -x) (21 -x) (20 -x) (19 -x) (18 -x) (17 -x) (16 -x) (15 -x) (14 -x) (13 -x) (12 -x) (11 -x) (10 -x) (9 -x) (8 -x) (7 -x) (6 -x) (5 -x) (4 -x) (3 -x) (2 -x) (1 -x)
```
Call c(x) the constraint polynomial, it checks whether an integer is in the range 1 to 10 and d(x) the domain polynomial. We started with 100 data points this polynomial vanishes on the numbers 1 to 100.

It is a mathematically fact that any polynomial that equals zero at all x from 1 to 100 must be a multiple of d(x). Now consider if we take our fitted polynomial we called f and calculated c(f(x)), so we are taking a degree 99 poynomial and composing it with a 10 degree polynomial the result is a 990 degree polynomial. Since if f(x) is “good” it evaluates to a number between 1 and 10. Then c(f(x)) is zero for all 1≤x≤100. d(x) vanishes on all x between 1 and 100 so c(f(x)) must be the product of a polynomial g(x) and d(x).

In other words
```
c(f(x)) = g(x) d(x) which means g(x) = c(f(x))/d(x)
```
Since c(f(x)) has degree 990 and g has degree 890 as d(x) has degree 100.

Basically you know the polynomial c(f(x)) so divide it byt the domain polynomial d(x) to get g(x). I used Mathematica, but basically its normal long division but with polynomials instead of numbers.

The first 10 terms of g(x) are
```
1.50209*10¹³⁵ — 6.97408*10¹³⁶ x + 1.60795*10¹³⁸ x² -2.45488*10¹³⁹ x³ + 2.79217*10¹⁴⁰ x⁴ — 2.52389*10¹⁴¹ x⁵ +1.88876*10¹⁴² x⁶ — 1.20373*10¹⁴³ x⁷ + 6.66973*10¹⁴³ x⁸ -3.26429*10¹⁴⁴ x⁹ + 1.42887*10¹⁴⁵ x¹⁰
```
Again with the caveat that the coefficients are just gross floating point approximations to the real rational coefficients.

Now Alice chooses a point x0 between 1 and 1000 at random, say x0=471.

now 
```
f(471)=3582690020558609293947647644718185784145638116842399606473778203172913101678697616115368433104647171034643185829243896680891483527297
```
Plugging this integer into the constraint polynomial gives an even bigger number
```
c(f(471))=348411386754414542878591691175653338905588493362393717532664064774454331997342472335873040158417498692420966404851007480261984174445430527325879012135396977001189546442584139288865554350871045572063244293120647596501131298497472400873884753201452564748895965367173753052139795368461551644159669238094064520495186423805990828224029331166226580819609658404780025352007632858398834253255940857031363480936722333543067300838617369278682058522916741755716993150549912219630732759568016892264451305190640111651864344370952082892462770070090383518940798999314973764198469409469792114425037439356632459189515425301398684055425159770782642075692252102841006054431403202948409492740894029602679452280544397557341358105721213409340532039360914559451771140611545127723549675371207346486686727394757444410506233369974987071870176607037853779173708520314417797006739364100857385538130311182076011748730617038669917361369813921131427110675728344116628957560570475952391411778550293407198111551232241656160495966189936637276908726016548240894655712341042579034524725722344361832180129997078107433573171910441755303704162398656626815087953875112831858336492563454343366397577273207573753853016969706292750739711779768060442302335200234990082862972293495074998396028900127160089883336646282445396967577997319725843115642926437280291518305484800
```
The value of g(471) is
```
g(471)=1068774830956021442510693804323332473549465301874081242969216329361376339171945254027385994971943723933445806386560299659915714577842303172776317019818881713499241528241195866658467691685370711250830656719466387143940526871262525826162631990017381524279465918438155179373793880636259551880320077200752724029115005893371455629413593627617238746938318371892561969202569519049182771832351142979419296069871002005971475771081918830820234340056369855293853521843056249412456671973845597062601241387344690819751016470708714178404404857722236110172501945170960551929491359459151261519214094925118315561332963343851686138751068904466393534704941241052642655693486766694243894916856899080667512661303603124626344481763599836090082246225370441872196759076440414193338452907770420818957204031101968184082010311512973102278064840564858845627883119006706669022325970700297358577345533999291692831003538297095534668117281550893503932475606553593203363843463829937941886304388991123790885202818008798530031069327859220436071326586026161673103795704872505885948557276123042290702544306226700551450874333336818762375307927134146934674127582075536954303405746698180457207146916781091180420477580933861971935979639307149358753791215762729942712155489557398354847576734787445156927171497940352400867826495535476018167252289564010167913740925707194263719116800000000000000000000000
```
```
d(x0) is

d(471)=18786003119436745984210109088544899515533693845512009586726408691138997958516390280802103340417768872492074685757541193892775761811301095626972986236746187100397675407920012468491413640433511853474129849283257052979646665230046541476003840000000000000000000000000
```
Now c(f(471))=g(471) d(471)

Dont bother checking this on a calculator the numbers are too large. I checked and yes it works.

Now if we change only one data point say the very first to 11, that is its outside of the range. We refit the polynomial f.
```
2.06381*10²⁹ + 1.06527*10³⁰ x — 2.58062*10³⁰ x² +3.94243*10³⁰ x³ — 4.29722*10³⁰ x⁴ + 3.58007*10³⁰ x⁵ -2.3827*10³⁰ x⁶ + 1.30659*10³⁰ x⁷ — 6.03972*10²⁹ x⁸ +2.39525*10²⁹ x⁹ — 8.26444*10²⁸ x¹⁰ + 2.50928*10²⁸ x¹¹ -6.76797*10²⁷ x¹² + 1.63456*10²⁷ x¹³ — 3.559*10²⁶ x¹⁴ +7.02736*10²⁵ x¹⁵ — 1.26478*10²⁵ x¹⁶ + 2.08427*10²⁴ x¹⁷ -3.15744*10²³ x¹⁸ + 4.41269*10²² x¹⁹ — 5.70738*10²¹ x²⁰ +6.8514*10²⁰ x²¹ — 7.65338*10¹⁹ x²² + 7.97399*10¹⁸ x²³ -7.76559*10¹⁷ x²⁴ + 7.08263*10¹⁶ x²⁵ — 6.06053*10¹⁵ x²⁶ +4.87339*10¹⁴ x²⁷ — 3.68815*10¹³ x²⁸ + 2.63053*10¹² x²⁹ -1.77046*10¹¹ x³⁰ + 1.12576*10¹⁰ x³¹ — 6.77013*10⁸ x³² +3.85451*10⁷ x³³ — 2.07953*10⁶ x³⁴ + 106403. x³⁵ -5167.42 x³⁶ + 238.365 x³⁷ — 10.4508 x³⁸ + 0.435771 x³⁹ -0.0172907 x⁴⁰ + 0.000653182 x⁴¹ — 0.0000235031 x⁴² +8.05876*10^-7 x⁴³ — 2.63408*10^-8 x⁴⁴ + 8.21014*10^-10 x⁴⁵ -2.44099*10^-11 x⁴⁶ + 6.92444*10^-13 x⁴⁷ — 1.87458*10^-14 x⁴⁸ +4.844*10^-16 x⁴⁹ — 1.19495*10^-17 x⁵⁰ + 2.81442*10^-19 x⁵¹ -6.32929*10^-21 x⁵² + 1.35914*10^-22 x⁵³ — 2.78691*10^-24 x⁵⁴ +5.45648*10^-26 x⁵⁵ — 1.02001*10^-27 x⁵⁶ + 1.82036*10^-29 x⁵⁷ -3.101*10^-31 x⁵⁸ + 5.04154*10^-33 x⁵⁹ — 7.82067*10^-35 x⁶⁰ +1.15725*10^-36 x⁶¹ — 1.63298*10^-38 x⁶² + 2.19658*10^-40 x⁶³ -2.8155*10^-42 x⁶⁴ + 3.4372*10^-44 x⁶⁵ — 3.99462*10^-46 x⁶⁶ +4.41694*10^-48 x⁶⁷ — 4.64376*10^-50 x⁶⁸ + 4.63895*10^-52 x⁶⁹ -4.39984*10^-54 x⁷⁰ + 3.95872*10^-56 x⁷¹ — 3.37575*10^-58 x⁷² +2.72545*10^-60 x⁷³ — 2.08098*10^-62 x⁷⁴ + 1.5008*10^-64 x⁷⁵ -1.02095*10^-66 x⁷⁶ + 6.5413*10^-69 x⁷⁷ — 3.94067*10^-71 x⁷⁸ +2.22803*10^-73 x⁷⁹ — 1.17984*10^-75 x⁸⁰ + 5.83815*10^-78 x⁸¹ -2.69255*10^-80 x⁸² + 1.15406*10^-82 x⁸³ — 4.58194*10^-85 x⁸⁴ +1.67883*10^-87 x⁸⁵ — 5.65258*10^-90 x⁸⁶ + 1.7403*10^-92 x⁸⁷ -4.87123*10^-95 x⁸⁸ + 1.23122*10^-97 x⁸⁹ — 2.78733*10^-100 x⁹⁰ +5.59628*10^-103 x⁹¹ — 9.84338*10^-106 x⁹² + 1.49331*10^-108 x⁹³ -1.9144*10^-111 x⁹⁴ + 2.0166*10^-114 x⁹⁵ — 1.67589*10^-117 x⁹⁶ +1.03026*10^-120 x⁹⁷ — 4.16516*10^-124 x⁹⁸ + 8.30655*10^-128 x⁹⁹
```
Compare this polynomial to the previous one, at a glance they are very similar.

Now f(x0) is
```
f(471)=3582690020558609293947647644632528781527622848341820638598715863016927666964705825150526076271713157876050735384250274135227496886697
```
Again almost the same as the previous answer but not quite look at the last digits.

Now c(f(x0))
```
c(f(471))=348411386754414542878591691092353151347871761714655731391476524271956472683096907206468540766081519545575907369732251064702151010832907886132491272240033224440976890604907993945516608199701579242787614040147297732164974884001460104411207271618578734537096693949905092527203545157217757181732796771033488150510739667127866857182713617990270278560659320475022938272225272535096767053715899504005807027859876437034408930121362398692990082013738514857624144916436832942366053089944834120542767307100538766253969861777472268987872287704871047094186498586115591279136567551650308682555214054752422148800277937681957227638900565399491427536420850167632156549135918873981287672337908663446716266803839795684700760937201195433512825505078702118730311900612367086972107801640939387127782263026852766718041863841880766889422346710742302693534808294434894697668136121834798593570089510706546703980892091463299050648669071992252717515680362381082524757292281269325557427754560271458518040843460287347401268331126447260034798869306930303981452561400801449814028058754288248311853431196953260859803283817729253913306774100577740660499925990640942947702196480388454160002274638823658364174723323632570130459437426983628102540381870922534446758370593666719831592448428230668734508322432875722034693459537371222066277655305958317251563243468800
```
The value of d(471)remains the same but now
```
c(f(471))<>g(471)d(471)
```
So the test fails.

Consider if Alice chooses the point x0 =1 then d(x0)=0 but c(f(xo)) <>0 so test fails again. So changing just one point in the data is immediately flagged. This property is known as Soundness.

So the test ensures that all the 100 numbers are between 1 and 10 if even 1 is 11, the test will fail!

Consider if Alice picks an x0 between 1 and 100 test will pass because 1≤f(x0)≤10 so c(f(x0))=0. d(x0) will vanish because it vanishes on all points 1 to 100. So Test will give 0 == 0. This property is known as Completeness, basically no false positives.

The test is too compare two polynomials of degree 990, g(x) is of degree 890 and d(x)of degree 100 so the two sides can only agree on 990 points out of 1000 points, so certainty is 99%.

An important point is that the degree of the interpolating polynomial f is related to the domain size. So its not just a bigger polynomial gives a better result its the ratio of degree/|domain|.

So far so good; but three things remain.

How do we use this to implement a zero knowledge proof between Alice and Bob
Can it be used for any program or just a list of numbers that must be in a particular range.
A more subltle point, Bob can cheat if he does not use a polynomial for g but some other function.
On point 1.

This comes form an Article Vitalik(I dont really have to say the rest do I) wrote.

First the Prover (Bob) commits ie, makes a Merkle tree and sends the verifier the root hash of the evaluations of f(x) and g(x) for all x. In our case 1≤x≤1000. This will include the 100 points where 1≤f(x)≤10 as well as the 900 other points where it does not. Alice the verifier either knows or can calculate the thousand points of d(x). Its the domain polynomial which is product of (1-x)(2-x)…(100-x). Now Alice picks a random number x0 between 1 and 1000 and asks Bob to provide the Merkle branches for f(x0) and g(x0). Bob provides these branches, Alice checks that i) the branches match the Merkle root that was provided earlier and ii) That c(f(xo)) actually equals g(x)d(x). Notice that Bob commits to the proof with the Merkle root before Alice chooses a random x0.

Point 2. yes it can be used for any program, it just involves changing the form of the constraint polynomial c.

Point 3. This point is more problematic, Pof Ben-Sassoon has an answer to this problem too, but I will leave that to another article.

