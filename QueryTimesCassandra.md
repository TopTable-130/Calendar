
### Find a restaraunt by ID

cqlsh:toptable> select * from restaraunt where restaraunt_id = 24000001;

 restaraunt_id | food_type | restaraunt_address  | restaraunt_name
---------------+-----------+---------------------+-----------------
      24000001 |    Indian | 68194 Goldner Alley |  Brady's Brunch

(1 rows)

Tracing session: 374c2e50-142f-11eb-90a4-3f16f6cb70ae

 activity                                                                                       | timestamp                  | source    | source_elapsed | client
------------------------------------------------------------------------------------------------+----------------------------+-----------+----------------+-----------
                                                                             Execute CQL3 query | 2020-10-21 23:24:18.869000 | 127.0.0.1 |              0 | 127.0.0.1
 Parsing select * from restaraunt where restaraunt_id = 24000001; [Native-Transport-Requests-1] | 2020-10-21 23:24:18.869000 | 127.0.0.1 |            125 | 127.0.0.1
                                              Preparing statement [Native-Transport-Requests-1] | 2020-10-21 23:24:18.869000 | 127.0.0.1 |            258 | 127.0.0.1
                                             Read-repair DC_LOCAL [Native-Transport-Requests-1] | 2020-10-21 23:24:18.871000 | 127.0.0.1 |           2771 | 127.0.0.1
                                   Executing single-partition query on restaraunt [ReadStage-2] | 2020-10-21 23:24:18.875000 | 127.0.0.1 |           6731 | 127.0.0.1
                                                     Acquiring sstable references [ReadStage-2] | 2020-10-21 23:24:18.875000 | 127.0.0.1 |           6811 | 127.0.0.1
                                                        Merging memtable contents [ReadStage-2] | 2020-10-21 23:24:18.876000 | 127.0.0.1 |           6845 | 127.0.0.1
                                          Bloom filter allows skipping sstable 86 [ReadStage-2] | 2020-10-21 23:24:18.876000 | 127.0.0.1 |           7562 | 127.0.0.1
                                          Bloom filter allows skipping sstable 85 [ReadStage-2] | 2020-10-21 23:24:18.876000 | 127.0.0.1 |           7630 | 127.0.0.1
                                          Bloom filter allows skipping sstable 80 [ReadStage-2] | 2020-10-21 23:24:18.876000 | 127.0.0.1 |           7665 | 127.0.0.1
                                          Bloom filter allows skipping sstable 74 [ReadStage-2] | 2020-10-21 23:24:18.876000 | 127.0.0.1 |           7699 | 127.0.0.1
                                          Bloom filter allows skipping sstable 69 [ReadStage-2] | 2020-10-21 23:24:18.878000 | 127.0.0.1 |           8879 | 127.0.0.1
                              Partition index with 0 entries found for sstable 40 [ReadStage-2] | 2020-10-21 23:24:18.881000 | 127.0.0.1 |          11912 | 127.0.0.1
                                           Read 1 live rows and 0 tombstone cells [ReadStage-2] | 2020-10-21 23:24:18.883000 | 127.0.0.1 |          14649 | 127.0.0.1
                                                                               Request complete | 2020-10-21 23:24:18.883821 | 127.0.0.1 |          14821 | 127.0.0.1



### Find a reservation by ID


cqlsh:toptable> select * from reservations_by_restaraunt where restaraunt_id = 20000100;

 restaraunt_id | reservation_id | booking_date | food_type | restaraunt_address    | restaraunt_name | time_slot | user_id
---------------+----------------+--------------+-----------+-----------------------+-----------------+-----------+----------
      20000100 |        5703385 |   2020-09-18 |  Japanese |   6733 Hackett Rapids |   Kallie's Cafe |  23:00 AM | 35206874
      20000100 |        8679581 |   2020-10-26 |   Mexican | 94149 Rodriguez Brook |   Maye's Dinner |  14:00 PM | 10093376

(2 rows)

Tracing session: b0fe5080-142e-11eb-90a4-3f16f6cb70ae

 activity                                                                                                       | timestamp                  | source    | source_elapsed | client
----------------------------------------------------------------------------------------------------------------+----------------------------+-----------+----------------+-----------
                                                                                             Execute CQL3 query | 2020-10-21 23:20:33.566000 | 127.0.0.1 |              0 | 127.0.0.1
 Parsing select * from reservations_by_restaraunt where restaraunt_id = 20000100; [Native-Transport-Requests-1] | 2020-10-21 23:20:33.615000 | 127.0.0.1 |          51321 | 127.0.0.1
                                                              Preparing statement [Native-Transport-Requests-1] | 2020-10-21 23:20:33.617000 | 127.0.0.1 |          52927 | 127.0.0.1
                                   Executing single-partition query on reservations_by_restaraunt [ReadStage-3] | 2020-10-21 23:20:33.618000 | 127.0.0.1 |          53478 | 127.0.0.1
                                                                     Acquiring sstable references [ReadStage-3] | 2020-10-21 23:20:33.618000 | 127.0.0.1 |          53720 | 127.0.0.1
                        Skipped 0/4 non-slice-intersecting sstables, included 0 due to tombstones [ReadStage-3] | 2020-10-21 23:20:33.618000 | 127.0.0.1 |          53982 | 127.0.0.1
                                                                    Key cache hit for sstable 164 [ReadStage-3] | 2020-10-21 23:20:33.618001 | 127.0.0.1 |          54195 | 127.0.0.1
                                                         Bloom filter allows skipping sstable 199 [ReadStage-3] | 2020-10-21 23:20:33.618001 | 127.0.0.1 |          54336 | 127.0.0.1
                                                         Bloom filter allows skipping sstable 189 [ReadStage-3] | 2020-10-21 23:20:33.618001 | 127.0.0.1 |          54363 | 127.0.0.1
                                                         Bloom filter allows skipping sstable 205 [ReadStage-3] | 2020-10-21 23:20:33.618001 | 127.0.0.1 |          54381 | 127.0.0.1
                                                        Merged data from memtables and 1 sstables [ReadStage-3] | 2020-10-21 23:20:33.618001 | 127.0.0.1 |          54486 | 127.0.0.1
                                                           Read 2 live rows and 0 tombstone cells [ReadStage-3] | 2020-10-21 23:20:33.619000 | 127.0.0.1 |          55217 | 127.0.0.1
                                                                                               Request complete | 2020-10-21 23:20:33.621517 | 127.0.0.1 |          55517 | 127.0.0.1



### Find a user by ID

cqlsh:toptable> select * from user where user_id = 22000100;

 user_id  | email                       | first_name | last_name | party_size | phone_number
----------+-----------------------------+------------+-----------+------------+--------------
 22000100 | Martina_Johns66@hotmail.com |     Deonte |   Roberts |          4 | 936-806-0446

(1 rows)

Tracing session: 5aaeb6b0-142f-11eb-90a4-3f16f6cb70ae

 activity                                                                           | timestamp                  | source    | source_elapsed | client
------------------------------------------------------------------------------------+----------------------------+-----------+----------------+-----------
                                                                 Execute CQL3 query | 2020-10-21 23:25:18.235000 | 127.0.0.1 |              0 | 127.0.0.1
 Parsing select * from user where user_id = 22000100; [Native-Transport-Requests-1] | 2020-10-21 23:25:18.235000 | 127.0.0.1 |            117 | 127.0.0.1
                                  Preparing statement [Native-Transport-Requests-1] | 2020-10-21 23:25:18.236000 | 127.0.0.1 |            336 | 127.0.0.1
                             Executing single-partition query on user [ReadStage-3] | 2020-10-21 23:25:18.236000 | 127.0.0.1 |            597 | 127.0.0.1
                                         Acquiring sstable references [ReadStage-3] | 2020-10-21 23:25:18.236000 | 127.0.0.1 |            684 | 127.0.0.1
                                            Merging memtable contents [ReadStage-3] | 2020-10-21 23:25:18.236000 | 127.0.0.1 |            727 | 127.0.0.1
                             Bloom filter allows skipping sstable 179 [ReadStage-3] | 2020-10-21 23:25:18.236000 | 127.0.0.1 |           1201 | 127.0.0.1
                 Partition index with 0 entries found for sstable 178 [ReadStage-3] | 2020-10-21 23:25:18.238000 | 127.0.0.1 |           2892 | 127.0.0.1
                               Read 1 live rows and 0 tombstone cells [ReadStage-3] | 2020-10-21 23:25:18.242000 | 127.0.0.1 |           6560 | 127.0.0.1
                                                                   Request complete | 2020-10-21 23:25:18.241831 | 127.0.0.1 |           6831 | 127.0.0.1



### Delete a reservation By id

cqlsh:toptable> delete from reservations_by_restaraunt where restaraunt_id = 5703385;

Tracing session: 066ec300-1430-11eb-90a4-3f16f6cb70ae

 activity                                                                                                    | timestamp                  | source    | source_elapsed | client
-------------------------------------------------------------------------------------------------------------+----------------------------+-----------+----------------+-----------
                                                                                          Execute CQL3 query | 2020-10-21 23:30:06.384000 | 127.0.0.1 |              0 | 127.0.0.1
 Parsing delete from reservations_by_restaraunt where restaraunt_id = 5703385; [Native-Transport-Requests-1] | 2020-10-21 23:30:06.385000 | 127.0.0.1 |            174 | 127.0.0.1
                                                           Preparing statement [Native-Transport-Requests-1] | 2020-10-21 23:30:06.385000 | 127.0.0.1 |            356 | 127.0.0.1
                                             Determining replicas for mutation [Native-Transport-Requests-1] | 2020-10-21 23:30:06.387000 | 127.0.0.1 |           3058 | 127.0.0.1
                                                                    Appending to commitlog [MutationStage-2] | 2020-10-21 23:30:06.388000 | 127.0.0.1 |           3333 | 127.0.0.1
                                             Adding to reservations_by_restaraunt memtable [MutationStage-2] | 2020-10-21 23:30:06.388000 | 127.0.0.1 |           3444 | 127.0.0.1
                                                                                            Request complete | 2020-10-21 23:30:06.388784 | 127.0.0.1 |           4784 | 127.0.0.1




### Insert a reservation



### update a reservation
