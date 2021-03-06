#Social Network Generation using Multiple threads

### Description
- This is a discrete time event social Network Simulator and Analyser.
- This project was created as part of a course(CSP301) project under Prof. Subodh Kumar , IIT Delhi , 2013.
- This project has been tested and developed on linux computers .
- C++ pthreads, message queues ,semaphores and mutexes etc have been used for achieving the desired Network Simulator and Analyser. 
- This project has been distributed in 2 parts.
	1. Network Generation,
	2. User queries over generated network.

### PartA

- This program produces "log.txt" , "graph.graphml".
- log.txt : Contains all log of all the events that took place in the simulation.
..- graph.graphml : Contains the generated graph saved in graphml format.

- A sample input file has been provided named as "SocialNetworkEnv.inp".
- The generic Structure of the graphml file is :
	1.	UNIVERSITY university_name
	2.	DEPARTMENT dept_name num_faculty num_students_per_year semester_dept_courses
	3.	semeseter_nondept_courses
	4.	COURSE course_number dept_that_offers frequency_per_year
	5.	INTEREST interest_name popularity
	6.	HOSTEL hostel_name
	7.	HOUSELOCALITY locality_name
	8.	FRIENDSHIPRATE req_per_minute
	9.	OPENNESS out_probability
	10.	FRIENDLINESS recip_probability
	11.	RANDOMSEED faculty_random student_random course_random friend_random
- This program produces "log.txt" , "graph.graphml" .
	1.	log.txt : Contains all log of all the events that took place in the simulation.
	2.	graph.graphml : Contains the generated graph saved in graphml format.

### PART B

Gyani: reads query from std::in and sends it to analyzer

Analyzer: first reads the graphml file and recieves query from Gyani and returns the result.

Algorithms.cpp : contains all the required algorithms
					1. Dijkstra's algorithm
					2. Floyd-Warshall algorithm
					3. Breadth First Search algorithms

Network.cpp: read graphml function, and stores the nodes

- A perl script will ask as input the name of the graphml file to be analysed.Please input the name of the graphml file copied earlier.
-Once the perl Script starts, it will take some time to preprocess the data and then it will present a UI where user can 
	ask questions regarding the generated graph.
-6 Questions are presently supported :
	1. Size of Clique of a given person (identified by university name and ID)
	2. The length of the shortest path between two given people
	3. The list of people on the shortest path between two given people
	4. The shortest path in the graph (between any pair of people)
	5. The importance of the given person (the importance is the number of the all-pair shortest paths that include that person)
	6. Is any of the friends of a given person more important that him/her
-Simple dictionary is maintained to detect the type of query from the keywords in the query.

## Compiling

Run **make** for the makefile present in the Final Simulation folder.

## Running 

- parta.sh would generate the network for analysis purposes. It takes two command line parameters as inputs.
	1.	Social Network Environment file(format as defined above). A sample is provided in the folder named as SocialNetworkEnv.inp.
	2. 	The number of years for which the network has to be started.(it starts from year 2012).
- partb.sh would parse the network generated and answer various queries asked . Details of the queries have been mentioned. It takes as input the network which is saved as graph.graphml. 

One can make changes to the parameters to generate social network and use it .

### Documentation
The code was documented using doxygen. The documentation is present in the top level directory of the repository.

