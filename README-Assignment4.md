Note: This assignment was done in team of two and this contains the documentation for the assignment 4 and rest of the assignment 1 - 3 is in README.md file
        
        Team members :
        
        Raj Kinkhabwala (rajparagbhai.kinkhabwala@sjsu.edu)
        Sakshi Jain (sakshi.jain01@sjsu.edu)
        
  Assignment # 4  
    
Team members contribution :

Raj Kinkhabwala:
1. Using nested paging to get the data set for exits
2. Restarting the KVM module with shadow paging after removing the KVM-intel module

Sakshi Jain :
1. Getting the data sets ready for Shadow Paging.
2. Compare the two data sets.

Steps follwowed :
(Same as assignment 3)

Total exits with EPT and without EPT - 

1. With EPT :
 
 https://github.com/rajkinkhabwala/linux/raw/master/With_EPT.png

2. Without EPT:
    
  https://github.com/rajkinkhabwala/linux/raw/master/Without_EPT.png

Learning from the count of exits :

Compared to nested paging, shadow paging resulted in a lot more exits. This was expected, as Nested paging executes a two-level page walk directly, allowing for faster page table modifications than shadow paging, which necessitates costly VMM intervention for page table updates.

What changed between the two runs : 

As we can see, when EPT is set to 0, the number of exits increases by roughly 200,000. The count was predicted to rise significantly, and it did, according to the findings. The following are the reasons why the count was predicted to rise: When EPT is set to zero, we use shadow paging instead of the nested paging method that is used when EPT is not set to zero. Now, during the shadow paging method, three types of exits are enabled and occur, resulting in an increase in the number of exits. CR3 exits, Page Fault Exits, and TLB Flush exits are the three types. These three forms of exits are in addition to the EPT violation exit, which is common in Nested paging. As a result, the number of exits is higher in this strategy, and the difference can be significant.
