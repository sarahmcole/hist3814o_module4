# HIST3814O: Module 4 Fail log
## August 6 2017

### Exercise 1: Network Visualization
+ Installed R x64 3.4.1
+ Installed RStudio 1.0.153
+ Installed Gephi 0.9.1
+ error trying to open my cleaned Texan correspondence csv: "Found row(s) with empty Source and/or Target columns." I opened my module3exercise2_returnofthecommandline.csv in excel and scanned through - for some reason, row 774 and 539 were blank. I deleted the blank rows and tried again.
 + still not working. I downloaded the file Dr. Graham provided. I'll compare it with my version later...
+ saved as module4exercise1.graphml.
+ uploaded graph file to github.

### Exercise 2: Topic Modelling
+ downloaded .zip (Windows) version of the [Topic Modeling Tool](https://github.com/senderle/topic-modeling-tool).
+ tried loading some files into it (including, inspired by Ian Cameron's topic mining of Geocities, a .txt file of [My Immortal (VERY NSFW)](http://myimmortal.wikia.com/wiki/My_Immortal/Chapters_1-11) the best worst fanfic ever)
 + fail: the topic modelling tool runs for a bit and seems to train a few topics (selections from My Immortal: `da draco 2 black blak vampire angrily fucking wuz suddenly wearing satan shouted looked 11 put 4 111 ur room`, then seems to freeze, with no output appearing in the /output_csv/ or /output_html/ folders in the output directory I set.
+ Cutting my losses: since the next exercise is a more in-depth exploration of topic modelling, I decide to move on to RStudio.


### Exercise 3: Topic Modelling in R
+ I use R as downloaded on my Windows computer.
+ stoplist provided in tutorial not working, downloaded en.txt from https://github.com/mimno/Mallet/tree/master/stoplists
 + used `> stoplist.file="C:\\Users\\Sarah\\Desktop\\mallet_stoplist.txt"`
+ made a bar graph of word.freqs with following code: `> View(word.freqs)
> counts <- table(word.freqs$term.freq)
> counts <- table(word.freqs$words)
> barplot(counts, main="Words", xlab="Number")
> freq.words <- table(word.freqs$term.freq)
> barplot(freq.words, main="Word Frequency", xlab="Word", ylab="Uses")`
 + fail: resulting graph didn't label each word on the X axis, just its relative prominence in the documents...
   + fixed fail: by manpulating the data in the top left window, I was able to find that "country" is the word used most frequently is "country". I'm not going to add it to the stoplist right now and see what my results come out like.
+ my list of words for topic 7 is:
`      words     weights
1      army 0.021212838
2     enemy 0.021212838
3      fort 0.019698355
4   general 0.019193527
5     force 0.014650078
6    quebec 0.011621112
7    troops 0.011621112
8       men 0.010106629
9   british 0.009601801
10 kingston 0.009096973`
 + question: is it meant to be different from the list in the tutorial? I think so, because it's algorithm-based, so my 1000 iterations would have been different from Dr. Graham's 1000 iterations, etc.
+ after running topics.labels:
` [1] "william james emigrants congress political"              
 [2] "south islands whale boats ship"                          
 [3] "labour situation settlement society manners"             
 [4] "people power men case opinion"                           
 [5] "states united congress state philadelphia"               
 [6] "meeting members held john committee"                     
 [7] "army enemy fort general force"                           
 [8] "number emigration united year emigrants"                 
 [9] "provision legislature citizens united proper"            
[10] "river miles governor country mountains"                  
[11] "esq company money sum amount"                            
[12] "bill house hear hon committee"                           
[13] "king chiefs strangers proceeded opposed"                 
[14] "america man work long young"                             
[15] "states united vessels colonies act"                      
[16] "indians men killed general body"                         
[17] "edinburgh understand congregation subscribed paisley"    
[18] "wild woodland cheer heart maraino"                       
[19] "hospital edinburgh medical motion court"                 
[20] "miles king coast bay north"                              
[21] "feet wife friend children horses"                        
[22] "colony south labour land colonization"                   
[23] "country land good acres price"                           
[24] "convicts society punishment transportation prisoners"    
[25] "wheat corn flour trees pork"                             
[26] "peru lima town thing produce"                            
[27] "persons settlers family families paid"                   
[28] "lord zealand court lordship emigration"                  
[29] "duke military death richmond inhabitants"                
[30] "arrived received town letter left"                       
[31] "church commission presbytery assembly south"             
[32] "great made time country place"                           
[33] "parliament legislative press constitution administration"
[34] "fire house houses fell distance"                         
[35] "american british americans america missionaries"         
[36] "steam cherokee table fair germany"                       
[37] "voyage bound nootka spaniards marriage"                  
[38] "wool sales bales market wools"                           
[39] "boat squadron long coming schooners"                     
[40] "negroes companies people regiment negro"                 
[41] "gold coin silver bank payments"                          
[42] "cape good colonial governor island"                      
[43] "south wales ship land passengers"                        
[44] "west north company fort river"                           
[45] "canada upper province quebec montreal"                   
[46] "ladies england hundred french understand"                
[47] "chief natives crew people fowler"                        
[48] "ditto june april sept john"                              
[49] "make world newspaper quakers dance"                      
[50] "free slaves whites president coloured" `
+ ran wordcloud; saved 5 examples as .pdf
+ ran network modelling; saved .graphml file
+ god, this was a difficult exercise. If I tried to change a few things, or even if I tried to copy out the code rather than copy&pasting it, I often got errors (check my R files for details on those). I didn't record many of the specific instances here because they were easily fixed by entering the code EXACTLY as Dr. Graham provided. That was frustrating, because I feel like I still don't understand mallet or RStudio very well. I'd like to work more with it this week.

### Exercise 5: Corpus Linguistics with AntConc
+ Followed [the linked tutorial](https://hfroehli.ch/workshops/getting-started-with-antconc/).
+ downloaded most recent version of AntConc (3.4.4) because I'm cutting-edge.
+ downloaded provided corpus of movie reviews.
+ saved results from searches for `wom?n` and `m?n` as module4exercise5_antconc_results_women.txt and module4exercise5_antconc_results_men.txt
 + as the tutorial seems aimed towards beginners to expressions and text searching, I didn't spend a long time playing around with searches. I did search and sort "damn," which gave me a lot of "damn them," "damn this movie," "damn dude" - which was funny.
+ my collocates list for "she" doesn't start with common words - I didn't sort the results! I sort by Freq(L) and they look much more like what I expected.
+ fail: accidentally loaded the spielberg corpus as the reference, which resulted in weird keyword list results. I redid this step with the spielberg corpus loaded and the general corpus as my reference corpus.
+ ran a few keyword searches & forgot to export them, but I did a keyword searche that I did save the results of for my [final project](https://github.com/sarahmcole/hist3814o_final_project/blob/master/antconc_results_keywordlist-1895vs1890-1900.txt).

### Antconc on the Equity for 1891
+ Loaded the equity files for 1891
+ using regex search, looked for /b*day (note: returns "day", "holiday", "today" as well as days of the week: I'm just playing around for now.)
 + Collocates -> Sort by Freq(L)
  + one of the most frequent collocates is "church" (66 with 39 instances - not bad considering the wonky OCR) - I would have expected this kind of result; church was a common gathering place.
  + ottawa is also a high collocate (74 with 37 instances) suggesting either frequent travel between the regions or an interest in federal politics or both.
+ looking at the concordence plot for `Monday|monday`, it seems like my hypothesis from last week (that days of the week are more frequently mentioned in the summer months, when weather is better and more events are taking place) may have some evidence to support it!
+ strongest collocate terms for `Monday|monday` is "on" and "every" - make sense, and suggest again that they often refer to events (tho not necessarily social events)
 + "visit" is also a high collocate (8th with a stat of 9.02) - worth looking into
 + "arranged" is 50th with a stat of 8.86
 + "suicide" is 56th with a stat of 8.57???????! sensationalism???!
+ "church" for search `Monday|monday` is 63rd collocate with stat of 5.86; "church" for search `Sunday|sunday` is 9th (and the first characteristic collocate, eg not "on," "the," "of," etc...) with a stat of 8.52!
 + suggests that even with crappy OCR, Antconc is picking up some patterns that reflect real life!
+ idea: compare one year of the equity to whole decade
 + idea x2: rigorously clean one year of equity, use that to create a "calendar," and compare that equity year to the entire decade - maybe 2 decades - of less cleaned articles for context (maybe do 1900 vs 1890-1910)
+ again forgot to save my stats, but I did more searches on a wider corpus for my [final project](https://github.com/sarahmcole/hist3814o_final_project/blob/master/antconc_results_sunday_equity1890-1900.txt).
 
 ## for more: see [faillog for final project](https://github.com/sarahmcole/hist3814o_final_project/blob/master/faillog_finalproject.md), section on Week 4.