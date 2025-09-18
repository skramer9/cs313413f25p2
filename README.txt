COMP 313/413 Project 2 Report Template

TestList.java and TestIterator.java

	TODO also try with a LinkedList - does it make any difference?

		When I swapped to a LinkedList, all the tests still pass, so assuming that the tests cover the possible
		 scenarios well, it does not seem to make a difference.

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

			This removes the item at list index 5.

		list.remove(Integer.valueOf(5)); // what does this one do?

			This removes the first occurrence of 5 in the list.

TestIterator.java

	testRemove()

		i.remove(); // what happens if you use list.remove(77)?

			Since list.remove(Integer.valueOf(77)) only removes the first occurrence of 77,
			there will still be other 2 more occurrences left, whereas the original implementation
			removes all 3 occurrences.

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000)
	to get the running time in milliseconds and how the test running times were recorded.

	SIZE 10
								  #1  #2  #3	... (as many tests as you ran)
        testArrayListAddRemove:  314 325 332
        testLinkedListAddRemove: 43  46  47
		testArrayListAccess:     28  27  28
        testLinkedListAccess:    30  29  28

	SIZE 100
								  #1   #2   #3
        testArrayListAddRemove:  333  356  328
        testLinkedListAddRemove: 48   45   45
		testArrayListAccess:     31   30   25
        testLinkedListAccess:    46   46   50

	SIZE 1000
								  #1   #2   #3
        testArrayListAddRemove:  473  522  516
        testLinkedListAddRemove: 57   50   49
		testArrayListAccess:     29   31   31
        testLinkedListAccess:    429  433  425

	SIZE 10000
								  #1   #2   #3
        testArrayListAddRemove:   2604 2638 2737
        testLinkedListAddRemove:  53   53   52
		testArrayListAccess:      29   32   30
        testLinkedListAccess:     5340 5376 5485

    SIZE 100000
								  #1    #2    #3
        testArrayListAddRemove:   21530 21182 20957
        testLinkedListAddRemove:  80    68    77
		testArrayListAccess:      63    57    62
        testLinkedListAccess:     51087 52932 49989

	listAccess - which type of List is better to use, and why?

		ArrayList. Since it is random access, it scales really well for access, because it does not have
		to traverse the list to find the nth element, which the linked list does.

	listAddRemove - which type of List is better to use, and why?

		LinkedList. Since we are adding at the beginning of the LinkedList, all you need to do is make
		the new element point to the first element and make the head pointer point to the new element,
		which is not really impacted by size of list. The array list needs to resize sometimes, which
		makes it take longer, and a linked list also does not need to resize.