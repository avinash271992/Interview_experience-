# Interview_experience-
Interview_experience 
1, how to convert little to big endian
   And through pointer 
2. How free() works ?
Ans. When you malloc a block, it actually allocates a bit more memory than you asked for. This extra memory is used to store information such as the size of the allocated block, and a link to the next free/used block in a chain of blocks, and sometimes some "guard data" that helps the system to detect if you write past the end of your allocated block. Also, most allocators will round up the total size and/or the start of your part of the memory to a multiple of bytes (e.g. on a 64-bit system it may align the data to a multiple of 64 bits (8 bytes) as accessing data from non-aligned addresses can be more difficult and inefficient for the processor/bus), so you may also end up with some "padding" (unused bytes).
When you free your pointer, it uses that address to find the special information it added to the beginning (usually) of your allocated block. If you pass in a different address, it will access memory that contains garbage, and hence its behaviour is undefined (but most frequently will result in a crash
Link https://stackoverflow.com/questions/1957099/how-do-free-and-malloc-work-in-c

3. Detail about structure padding ?
4. what is Interrupt top half and bottom half ?

