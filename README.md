# SUBTLEXus

#TASK1:	
This	lexicon	provides	a	list	of	words	with	their	frequency	counts	extracted	from	a	
corpus	of	subtitles	from	movies	and	web	series.	1	point:	Your	notebook	should	show	the	
first	10	lines	of	the	Pandas	df storing	the	dataset.

#TASK2:	
create	two	iterables	of	strings	(e.g.	list	or	set	of	strings).	The	first	contains	word	
types	from	SUBTLEX	and	the	other	word	tokens	from	SUBTLEX.	Mind	the	difference	and	
the	relation	between	types/tokens	and	frequency.	2	points:	Your	iterables	should	
contain	the	right	items	and	the	right	number	of	items.


#TASK3:	
implement	a	character	level	language	model	with	Laplace	smoothing	and	a	
constant	k=0.01	which	takes	the	following	input	arguments:
- an	iterable	containing	the	target	strings
- the	size	of	the	character	ngrams
and	estimates	a	transition	matrix.	You're	free	to	implement	it	as	a	class	or	as	a	series	of	
functions.	It's	important	that	you	can	use	the	language	model	to	compute	the	perplexity	
of	a	string	under	the	language	model and	to	generate	new	strings	given	the	BoS	symbol.	
10	points,	awarded	following	this	scheme:
- 1	point	if	your	LM	prepends	the	right	number	of	BoS	symbols	and	appends	the	right	
amount	of	EoS	symbols
- 1	point	if	your	LM	has	the	the	right	vocabulary
- 4	points	if	your	model	estimates	the	right	transition	matrix
- 2	points	if	your	model	computes	perplexity	correctly
- 2	points	if	your	model	generates	strings	correctly


#TASK4:	
find	the	word	from	SUBTLEX	with	the	lowest	perplexity	given	the	following	
language	models:
- trigram,	token-based
- trigram,	type-based
- tetragram,	token-based
- tetragram,	type-basedDo	this	for	words	of	length	3,	of	length	8,	and	of	length	13.	Your	notebook	should	show	a	
Pandas	df	with	4	columns	storing	the	following	pieces	of	information: ngram	size,	input	
dataset	(types	or	tokens),	the	word	with	lowest	perplexity,	and	the	perplexity	
score. Comment	on	your	results	by	highlighting	differences	and	similarities	across	
models.	7	points:	your	code	should	return	the	right	words	and	corresponding	perplexity	
scores	for	all	LMs	(4	points),	and	your	comments	must	be	appropriate	(3	points).


#TASK5:	
starting	from	the	BoS	symbol,	generate	the	likeliest	string	given	the	following	
language	models	(make	sure	you	don't	generate	strings	longer	than	50	characters):
- trigram,	token-based
- trigram,	type-based
- tetragram,	token-based
- tetragram,	type-based
Your	notebook	should	show	a	Pandas	df	with	3	columns	storing	the	following	pieces	of	
information: ngram	size,	input	dataset	(types	or	tokens),	and	the	string	each	model	
generates	as	the	likeliest.	Comment	on	similarities	and	differences	across	them	and	
explain	what	these	strings	represent	in	terms	of	English	orthotactics. . 7	points:	the	
generated	strings	need	to	be	correct	(4	points)	and	your	comments	on	point	(3	points).



#TASK6:	
starting	from	the	BoS	symbol,	generate	10	different	strings,	according	to	the	LM	
probabilities,	given	the	following	language	models	(make	sure	you	don't	generate	
strings	longer	than	50	characters):
- trigram,	token-based
- trigram,	type-based
- tetragram,	token-based
- tetragram,	type-based
For	each	generated	string,	compute	its	length	and	the	average	Levensthein	distance	
from	the	target	to	the	20	closest	neighbors	in	SUBTLEX	(OLD20).	Your	notebook	should	
show	a	Pandas	df	with	4	columns	storing	the	following	pieces	of	information: ngram	
size,	input	dataset	(types	or	tokens),	the	average	OLD20	of	the	generated	strings,	and	the	
average	length	of	the	generated	strings. Which	language	model	generates	new	strings	
with	denser	orthographic	neighbourhoods	(lower	OLD20	values)?	How	does	the	length	
of	generated	strings	factor	in?	What	does	that	tell us	with	respect	to	the	different	
language	models	and	their	ability	to	capture	English	orthotactics?	In	solving	this	task,	
you	can	make	use	of this	Python	package (Links to an external site.), but	you	don't	have	
to,	you	can	use	whatever	solution	you	see	fit.	8	points:	since	there's	randomness	
involved,	points	are	not	awarded	based	on	output,	but	based	on	whether	the	code	runs	
(4	points)	and	whether	your	comments	reflect	the	findings	(4	points).
To	install	the	extra	Python	package	from	GitHub:
1.	open	the	terminal
2.	go	to	the	folder	where	your	notebook	is
3.	clone	the	repo
4. cd	to	the	package	folder
4.	run	pip	install	.
5.	check	the	requirements	of	the	package	and	install	the	necessary	modules.


#TASK7: 
visit the NorthEuraLex (Links to an external site.) dataset	and	fetch	the	
appropriate	translations	for	the	concepts MOUTH,	DREAM,	SUN,	APPLE,	BRIDGE,	
MIRROR,	SKY,	FISH,	ROOSTER,	SON in English,	Czech,	Dutch,	Finnish,	Italian,	and	
Basque.	Compute	the	perplexity	for	each	translation	given	the	following	language	models	trained	on	SUBTLEX:
- trigram,	token-based
- trigram,	type-based
- tetragram,	token-based
- tetragram,	type-based
then	find:
>	the	non-English	string	with	the	lowest	perplexity	(for	each	different	language	model)	-
provide	a	Pandas	df	with	the	ngram	size,	the	input	dataset,	the	concept,	the	language,	
the	word,	and	the	corresponding	perplexity.
>	the	non-English	string	with	the	highest	perplexity	(for	each	different	language	model)	
- provide	a	Pandas	df	with	the	ngram	size,	the	input	dataset,	the	concept,	the	language,	
the	word,	and	the	corresponding	perplexity.
>	the	average	perplexity	for	each	language	- provide	a	Pandas	df	with	the	ngram	size,	
the	input	dataset,	the	language,	and	the	corresponding	average	perplexity
What	can	you	say	about	relations	between	the	target	languages	and	English	based	on	
how	perplex	the	language	models	are	when	fed	with	translations	of	these	10	core	
concepts?	10	points:	you	should	have	identified	the	correct	translations	(1	point,	only	
awarded	if	all	words	are	correct),	your	code	should	return	the	right	perplexity	scores	
for	all	LMs	(4	points),	and	your	comments	must	be	appropriate	(4	points).	If	you	didn't	
retrieve	correct	words,	perplexity	scores	will	be	evaluated	only	for	the	correct	ones.
