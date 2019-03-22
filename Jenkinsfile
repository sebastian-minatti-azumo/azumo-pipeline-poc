pipeline {
    agent any
    stages {
        stage('etlJobScriptWrapper_copy_dropbox_csvsPhase') {
            steps {
                build 'etlJobScriptWrapper_copy_dropbox_csvs'
            }
        }
        stage('etlJobCalcVerifyDataPreRunPhase') {
            steps {
                build 'etlJobCalcVerifyDataPreRun'
            }
        }
        stage('etlJobCopyTablesFromAWSPhase') {
            steps {
                build 'etlJobCopyTablesFromAWS'
            }
        }
        stage('etlJobCreateNewMarketSnapshotRecordPhase'){
            steps {
                build 'etlJobCreateNewMarketSnapshotRecord'
            }
        }
        stage('etlCollection_symbol_fullPhase'){
            steps {
                build 'etlCollection_symbol_full'
            }
        }
        stage('etlCollection_ssg_dailyPhase'){
            steps {
                build 'etlCollection_ssg_daily'
            }
        }
        stage('etlCollection_stock_dailyPhase'){
            steps {
                build 'etlCollection_stock_daily'
            }
        }
        stage('etlJobCalcSSGChangeCoefficientPhase'){
            steps {
                build 'etlJobCalcSSGChangeCoefficient'
            }
        }
        stage('etlJobCalcMapsPhase'){
            steps {
                build 'etlJobCalcMaps'
            }
        }
        stage('etlJobCalcSACAPhase'){
            steps {
                build 'etlJobCalcSACA'
            }
        }
        stage('etlJobPurgeInactiveDatasetsPhase'){
            steps{
                build 'etlJobPurgeInactiveDatasets'
            }
        }
        stage('ParallelPhase1'){
            parallel {
                stage('etlJobCalcStockCompositeScore'){
                    steps {
                        build 'etlJobCalcStockCompositeScore'
                    }
                }
                stage('etlJobCalcSSGComposite'){
                    steps {
                        build 'etlJobCalcSSGComposite'
                    }
                }
                stage('etlJobCalcStockActionCategoryFeatureGen'){
                    steps {
                        build 'etlJobCalcStockActionCategoryFeatureGen'
                    }
                }
            }
        }
        stage('etlJobCalcSP15DayVolatilityPhase'){
            steps {
                build 'etlJobCalcSP15DayVolatility'
            }
        }
        stage('etlJobScriptWrapper_create_dumpPhase'){
            steps {
                build 'etlJobScriptWrapper_create_dump'
            }
        }    
        stage('talend_symbol_static_phase'){
            steps {
                build 'talend_symbol_static'
            }
        }
        stage('talend_symbol_snapshot_phase'){
            steps {
                build 'talend_symbol_snapshot'
            }
        }
        stage('talend_symbol_phase'){
            steps {
                build 'talend_symbol'
            }
        }
        stage('talend_map_type_phase'){
            steps {
                build 'talend_map_type'
            }
        }
        stage('talend_map_xy_header_phase'){
            steps {
                build 'talend_map_xy_header'
            }
        }
        stage('talend_map_xy_phase'){
            steps {
                build 'talend_map_xy'
            }
        }
        stage('talend_ssg_hierarchy_phase'){
            steps {
                build 'talend_ssg_hierachy'
            }
        }
        stage('talend_market_snapshot_phase'){
            steps {
                build 'talend_market_snapshot'
            }
        }
        stage('talend_key_observation_phase'){
            steps {
                build 'talend_key_observation'
            }
        }
        stage('talend_market_comment_phase'){
            steps {
                build 'talend_market_comment'
            }
        }
        stage('talend_symbol_comment_phase'){
            steps {
                build 'talend_symbol_comment'
            }
        }
        stage('talend_ssg_comment_phase'){
            steps {
                build 'talend_ssg_comment'   
            }
        }
        stage('talend_ssg_snapshot_phase'){
            steps {
                build 'talend_ssg_snapshot'   
            }
        }
        stage('talend_symbol_stovell_phase'){
            steps {
                build 'talend_symbol_stovell'
            }
        }
        stage('talend_etl_active_phase'){
            steps {
                build 'talend_etl_active'
            }
        }
        stage('Post Data Migration Processing'){
            steps {
                build 'etlJobPurgeInactiveDatasetsProd'
                build 'etlJobWebCacheUpdate'
            }
        }
        stage('etlJobScriptWrapper_ml_daily_phase1'){
            steps {
                build 'etlJobScriptWrapper_ml_daily_phase1'
            }
        }
        stage('etlJobScriptWrapper_ml_daily_phase2'){
            steps {
                build 'etlJobScriptWrapper_ml_daily_phase2'
            }
        }
        stage('etlJobMLDataCohortExportConsumer'){
            steps {
                build 'etlJobMLDataCohortExportConsumer_1_Tech_New'
                build 'etlJobMLDataCohortExportConsumer_2_Tech_Old'
                build 'etlJobMLDataCohortExportConsumer_3_Bio_AND_Spec'
                build 'etlJobMLDataCohortExportConsumer_4_Old_Health'
                build 'etlJobMLDataCohortExportConsumer_5_Defensive'
                build 'etlJobMLDataCohortExportConsumer_6_Cons_Discr_AND_Svc'
                build 'etlJobMLDataCohortExportConsumer_7_Cons_Dur'
                build 'etlJobMLDataCohortExportConsumer_8_Lenders'
                build 'etlJobMLDataCohortExportConsumer_9_Non-Lender_Financials'
                build 'etlJobMLDataCohortExportConsumer_10_REITs'
                build 'etlJobMLDataCohortExportConsumer_11_Materials'
                build 'etlJobMLDataCohortExportConsumer_12_Industrial_Broad'
                build 'etlJobMLDataCohortExportConsumer_13_Oil_AND_Gas'
                build 'etlJobMLDataCohortExportConsumer_14_RE'
            }
        }
}