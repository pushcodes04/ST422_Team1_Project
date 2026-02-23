# Management Plan

**ST422 Statistical Consulting \| Brief 8: Road Safety Analysis
 \| Team 1 \| February 2026**

This plan sets out how Team 1 will organise and deliver the consultancy.
Roles are provisional and will be confirmed at the first team meeting.
The document is live and will be updated as work progresses.

------------------------------------------------------------------------

# 1. Workplan and Milestones

## 1.1 Delivery Approach

At the macro level, we are using a waterfall structure, with phases
running broadly in sequence and defined handover points between them.
Within each phase, work is organised in weekly sprints reviewed every
Sunday evening. This approach provides overall structure while keeping
individual weeks flexible.

The project runs from Week 6 (16 February) with a target internal
completion date of 20 April. This provides a one-week buffer before the
formal deadline of 27 April. As exams begin around that time, we aim to
avoid relying on the final week.

------------------------------------------------------------------------

## 1.2 Phases of Work

Each phase concludes with a defined deliverable and clear completion
criteria.

  ------------------------------------------------------------------------------------------
  Phase            Key Activities      Deliverable       Completion Criteria   Target Date
  ---------------- ------------------- ----------------- --------------------- -------------
  Triage and Scope Read Brief 8. Agree Agreed scope note All team members have 23 Feb 2026
                   the decision        (SELECTION.md).   read the brief. Scope 
                   question, scope     Repository and    documented and        
                   boundaries, and     workspace         agreed.               
                   exclusions. Set up  established.                            
                   Notion workspace                                            
                   and GitHub                                                  
                   repository.                                                 

  Data Readiness   Download STATS19    Clean joined      Cleaning script runs  13 Mar 2026
                   datasets            dataset and       from repository root. 
                   (accidents,         concise data      No manual             
                   vehicles,           dictionary.       intervention          
                   casualties). Join                     required.             
                   tables, clean,                                              
                   assess missingness,                                         
                   document                                                    
                   exclusions.                                                 

  Analysis         Severity and trend  Core figures and  All principal claims  30 Mar 2026
                   analysis. Hotspot   tables saved to   supported by a figure 
                   identification.     outputs           or table.             
                   Contributory factor directory.                              
                   analysis. At least  Results notes                           
                   two robustness      drafted.                                
                   checks.                                                     

  Interpretation   Translate findings  Draft findings    Recommendations       6 Apr 2026
                   into                section with      follow directly from  
                   decision-relevant   recommendations   evidence. Limitations 
                   insights. Draft     and rationale.    framed as decision    
                   limitations and                       risks.                
                   uncertainty                                                 
                   framing. Agree                                              
                   recommendations.                                            

  Reporting        Write executive     Full draft report Narrative aligns with 13 Apr 2026
                   summary, client     (Version 1).      evidence. Each claim  
                   report, technical                     has an anchored       
                   report, and                           figure or table.      
                   traceability table.                   Traceability table    
                                                         complete.             

  QA and           Peer review of      Final report,     Fresh run reproduces  20 Apr 2026
  Finalisation     claims and figures. reproducibility   all outputs. All      
                   Full                record, QA log.   compliance            
                   reproducibility run                   requirements          
                   from a fresh clone.                   satisfied.            
                   Resolve issues.                                             
                   Prepare submission.                                         
  ------------------------------------------------------------------------------------------

------------------------------------------------------------------------

## 1.3 Milestones

Internal deadlines are scheduled at least one week before they become
critical, allowing time for revision if necessary.

  ------------------------------------------------------------------------------------
  Milestone         Milestone Definition   Rationale         Date     Owner   Status
  ----------------- ---------------------- ----------------- -------- ------- --------
  Scope agreed      Decision question      Prevents scope    23 Feb   All     Open
                    confirmed.             creep from the                     
                    Out-of-scope list      outset.                            
                    documented.                                               
                    SELECTION.md                                              
                    submitted.                                                

  Repository and    GitHub repository      Establishes       23 Feb   All     Open
  workspace live    created. Folder        shared governance draft;           
                    structure agreed.      and a single      28 Feb           
                    Notion workspace       working           v1               
                    operational.           environment.                       

  Data freeze v1    Clean STATS19 dataset  Prevents dataset  13 Mar   All     Open
                    produced via code.     drift during                       
                    Version tagged. Data   analysis.                          
                    dictionary completed.                                     

  First figures     Core plots and tables  Enables early     23 Mar   All     Open
  completed         drafted, including     narrative                          
                    initial versions.      drafting and                       
                                           identifies data                    
                                           issues.                            

  Draft             Recommendation and     Ensures the       6 Apr    All     Open
  recommendations   supporting rationale   report remains                     
  prepared          drafted.               decision-led                       
                                           rather than                        
                                           descriptive.                       

  First full        Report renders from    Identifies        13 Apr   All     Open
  reproducible      repository root        reproducibility                    
  build             without manual edits.  issues while time                  
                                           remains to                         
                                           address them.                      

  Peer review       Sections reviewed by   Improves clarity  17 Apr   All     Open
  completed         non-authors and        and reduces                        
                    comments addressed.    avoidable errors.                  

  Final submission  Portfolio submitted to Hard deadline.    27 Apr   All     Open
                    Moodle.                                  1pm              
  ------------------------------------------------------------------------------------

------------------------------------------------------------------------

## 1.4 Roles and Responsibilities

Roles are assigned to establish accountability and maintain momentum.
Leading a role means owning the process, not completing all associated
tasks alone. Names will be confirmed at the first meeting.

  ------------------------------------------------------------------------------
  Role        Responsibilities            Outputs           Assigned To
  ----------- --------------------------- ----------------- --------------------
  Project     Maintains schedule, chairs  Meeting notes,    Yadavan Surabaskaran
  Lead        weekly reviews, records     action log,       
              actions, escalates risks    status updates.   
              where necessary.                              

  Data        Oversees data acquisition,  Clean dataset,    Zahid Ahmed
  Steward     cleaning, documentation,    data dictionary,  
              and version tagging.        cleaning script.  

  Analysis    Coordinates modelling,      Figures, tables,  Pushkal Ahluwalia
  Lead        trend analysis, hotspot     results           
              analysis, and robustness    documentation.    
              testing.                                      

  Reporting   Leads drafting of executive Draft and final   Caleb Sithole
  Lead        summary, client report,     reports.          
              technical report, and                         
              traceability table.                           

  QA Lead     Conducts reproducibility    Reproducibility   Akeel Shah
              checks, reviews code and    record, QA log,   
              figures, maintains QA log.  validation notes. 
  ------------------------------------------------------------------------------

------------------------------------------------------------------------

# 2. Risk Register

The following risks have been identified as most likely to affect
delivery or validity. The register will be reviewed weekly and updated
accordingly.

  --------------------------------------------------------------------------------------------
  Risk              Likelihood   Impact   Early Indicator  Mitigation     Owner       Status
  ----------------- ------------ -------- ---------------- -------------- ----------- --------
  Scope creep       Medium       High     Tasks introduced Freeze scope   Project     Open
                                          that are not     at Week 7.     Lead        
                                          linked to the    Maintain an                
                                          decision         out-of-scope               
                                          question         record.                    
                                                           Require full               
                                                           team agreement             
                                                           for additions.             

  STATS19 data      Medium       High     High missingness Assess data    Data        Open
  quality issues                          or inconsistent  quality during Steward     
                                          coding across    triage.                    
                                          years            Document                   
                                                           exclusions.                
                                                           Run                        
                                                           sensitivity                
                                                           analyses where             
                                                           required.                  

  Uneven            Low          High     Agreed tasks not Assign each    Project     Open
  contribution                            completed on     task to a      Lead        
                                          schedule         named owner.               
                                                           Review weekly              
                                                           progress.                  
                                                           Escalate                   
                                                           concerns                   
                                                           early.                     

  Reproducibility   Medium       High     Code dependent   Use relative   QA Lead     Open
  failure                                 on local paths   paths from                 
                                          or missing       outset.                    
                                          dependencies     Maintain                   
                                                           renv.lock.                 
                                                           Conduct early              
                                                           clean-run                  
                                                           test.                      

  Writing           Medium       High     No draft         Begin          Reporting   Open
  compressed into                         narrative by     executive      Lead        
  final weeks                             early April      summary                    
                                                           skeleton                   
                                                           early. Lock                
                                                           figures before             
                                                           final writing              
                                                           stage.                     

  Exam period       High         Medium   Reduced team     Target         All         Open
  impact                                  availability in  internal                   
                                          late April       completion by              
                                                           20 April.                  
                                                           Avoid planning             
                                                           substantial                
                                                           work in final              
                                                           week.                      
  --------------------------------------------------------------------------------------------

------------------------------------------------------------------------

# 3. Quality Assurance and Validation

## 3.1 Data Quality Checks

These checks are performed each time the dataset is updated. Results are
recorded.

  -------------------------------------------------------------------------------
  Check         Method        Acceptance Threshold          Timing      Owner
  ------------- ------------- ----------------------------- ----------- ---------
  Missingness   Scripted      Flag if greater than 10       Each data   Data
  assessment    summary of    percent in variables used in  update      Steward
                percentage    primary claims                            
                missing by                                              
                variable                                                

  Duplicate     Check         No duplicates in              Each data   Data
  detection     accident      accident_index                update      Steward
                reference                                               
                identifiers                                             
                and full-row                                            
                duplication                                             

  Range and     Rule-based    Values must fall within       Each data   Data
  validity      constraints   documented valid ranges       update      Steward
  checks        for severity                                            
                codes, dates,                                           
                casualty                                                
                counts                                                  

  Year          Confirm       Any material change flagged   At data     Data
  consistency   consistent    and documented                freeze      Steward
  review        coding                                                  
                definitions                                             
                across years                                            
  -------------------------------------------------------------------------------

------------------------------------------------------------------------

## 3.2 Robustness Checks

Each robustness check is directly linked to a principal claim. Material
change thresholds are defined in advance.

  -------------------------------------------------------------------------------
  Check         Rationale        Adjustment     Threshold for Reassessment
  ------------- ---------------- -------------- ---------------------------------
  Alternative   Severity         Restrict       If direction or magnitude of
  severity      classification   analysis to    trend changes materially
  filter        changed in 2016  post-2016 data 
                                 and compare    
                                 results        

  Alternative   Geographic unit  Compare police If priority areas change
  hotspot       choice may       force area     substantially
  definition    affect           with local     
                priorities       authority      
                                 geography      

  Alternative   Grouping         Re-run         If ranking of top factors changes
  factor        decisions        analysis with  materially
  grouping      influence factor alternative    
                prominence       grouping       
                                 schemes        

  Excluding     2020 and 2021    Re-run trends  If overall trend direction
  COVID years   had atypical     excluding      changes
                collision        those years    
                volumes                         
  -------------------------------------------------------------------------------

------------------------------------------------------------------------

## 3.3 Review Process

Review is scheduled as a formal milestone rather than a final-stage
activity.

  --------------------------------------------------------------------------------
  Review Type         Scope             Method       Date      Responsible
  ------------------- ----------------- ------------ --------- -------------------
  Narrative review    Claims, executive Non-author   17 Apr    All
                      summary,          review with  2026      
                      recommendations   comments               
                                        recorded               

  Figure validation   Labels, units,    Checklist    17 Apr    All
                      comparators,      review       2026      
                      clarity           against                
                                        associated             
                                        claim                  

  Code verification   Full analytical   Fresh clone  13 Apr    QA Lead
                      pipeline and      build        2026      
                      dependency        following              
                      restoration       README                 
  --------------------------------------------------------------------------------

------------------------------------------------------------------------

## 3.4 Reproducibility Verification

A full clean build will be completed by 13 April.

Date of clean run: To be completed\
Executed by: To be completed\
Environment details: Operating system, R version, dependencies restored
via renv.lock

Procedure\
1. Clone repository\
2. Restore dependencies\
3. Render report from project root

Outputs verified\
Key figures and tables listed with file paths

Outcome\
Pass or fail. Any issues recorded and resolved before final submission.

------------------------------------------------------------------------

Last updated: 23 February 2026\
