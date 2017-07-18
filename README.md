# The Quran Holy Book
Source of this database :  [Alfanous-team/alfanous-api/tree/master/resources/databases](https://github.com/Alfanous-team/alfanous-api/tree/master/resources/databases).

## Database Tables 

### Aya Table 

	`TABLE aya
			(
		            --global aya id
		                 gid int,
		                 
		            --sura_aya key
		                 sura_id int,
		                 aya_id int,
		               
		                 
		            --aya texts
		                 standard text ,
		                 standard_full text ,
		                 uthmani text ,
		                 uthmani_min text,
		                 
		            --subjects
		                 chapter text,
		                 topic text,
		                 subtopic text ,
		                 subject text,
		                 
		            --structures
		                 rub_gid int ,
		                 nisf_gid int ,
		                 hizb_gid int ,
		                 juz_gid int ,
		                 rub_id int ,
		                  nisf_id int,
		                  hizb_id int,
		                 juz_id int ,
		                  page_id int,
		                  ruku_id int,
		                 manzil_id int ,
		                 sajda varchar(10),--bool
		                 sajda_id int ,
		                 sajda_type varchar(10),
		                 
		            --sura info
		                 sura_name varchar(20),
		                 sura_type varchar(30) ,
		                  sura_order int,
		                 
		                 
		            --statistiques
		                 sura_ayas_nb int,
		                 sura_gnames_nb int ,
		                 sura_words_nb int,
		                 sura_letters_nb int,
		                 sura_rukus_nb int ,
		                 aya_gnames_nb int,
		                 aya_words_nb int,
		                 aya_letters_nb int, 
				 page_id_indian integer, 
                                 sura_name_en VARCHAR(25), 
                                 sura_name_romanization VARCHAR(25),
				 sura_type_en varchar(10),
		            
		              primary key(gid)
		              unique(sura_id,aya_id)
		            
		            );`

### Field Table

	`TABLE field 
                        (
                        id int  ,
                        name varchar(20) ,
                        name_arabic varchar(20) ,
                        table_name varchar(10) ,
                        comment text ,
                        type varchar(20) ,
                        format varchar(20) ,
                        is_indexed int ,--bool
                        is_stored int ,--bool
                        is_spellchecked int ,--bool
                        is_scorable int ,--bool
                        is_unique int ,--bool
                        source varchar(30),
                        source_comment text,
                        revised int,
                        revised_by varchar(30), 'search_name' varchar(20), analyser varchar(20), boost varchar(20), phrase varchar(20), lock int,
                        
                        primary key(id)
                        ); 
`

### Synonymes Table

	`TABLE synonymes(id int primary key,word varchar(15) unique,synonymes varchar(120));`


### Stopwords Table

	`TABLE stopwords(id int primary key,word varchar(10) unique,nb_in_quran int );`

### Word Table 

	`TABLE word 
                        (-- global word id
                         id int ,
                        
                        --sura_aya_word key
                        --sura_id int,
                        --aya_id int ,
                        --word_id int,
                        
                        
                        --word tokens
                         word varchar(20),
                         word_ varchar(20),

                        uthmani varchar(20) ,
                        
                        --stems
                        lemma varchar(20) ,
                        root varchar(10) ,
                        
                        --class
                        type varchar(50) ,
                        pattern varchar(20) ,            
                        gender varchar(20) ,
                        number varchar(20) ,
                        person varchar(20) ,
                        i3rab varchar(20) ,
                     
                       
                        --affixes
                        --prefix varchar(10) ,
                        --suffix varchar(20) ,
                        
                        --synonymes
                        --synonymes varchar(100) ,
                        
                        --statistiques
                        --word_letters_nb  int ,
                        
                        primary key(id)
                        --unique(sura_id,aya_id,word_id)
                         
                         
                         
                         );`

