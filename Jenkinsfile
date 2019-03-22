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
        stage('SR Daily Multijob Data Migration Phase') {
            parallel {
                stage('SR Daily Multijob Data Migration'){
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
                }
                stage('Post Data Migration Processing'){
                    stage('etlJobPurgeInactiveDatasetsProd'){
                        steps {
                            build 'etlJobPurgeInactiveDatasetsProd'
                        }
                    }
                    stage('etlJobWebCacheUpdate'){
                        steps {
                            build 'etlJobWebCacheUpdate'
                        }
                    }
                }
                stage('SR Daily ML Data Gen'){
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
                        parallel {
                            stage('etlJobMLDataCohortExportConsumer_1_Tech_New'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_1_Tech_New'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_2_Tech_Old'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_2_Tech_Old'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_3_Bio_AND_Spec'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_3_Bio_AND_Spec'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_4_Old_Health'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_4_Old_Health'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_5_Defensive'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_5_Defensive'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_6_Cons_Discr_AND_Svc'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_6_Cons_Discr_AND_Svc'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_7_Cons_Dur'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_7_Cons_Dur'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_8_Lenders'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_8_Lenders'
                                }
                            }                            
                            stage('etlJobMLDataCohortExportConsumer_9_Non-Lender_Financials'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_9_Non-Lender_Financials'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_10_REITs'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_10_REITs'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_11_Materials'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_11_Materials'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_12_Industrial_Broad'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_12_Industrial_Broad'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_13_Oil_AND_Gas'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_13_Oil_AND_Gas'
                                }
                            }
                            stage('etlJobMLDataCohortExportConsumer_14_RE'){
                                steps {
                                    build 'etlJobMLDataCohortExportConsumer_14_RE'
                                }
                            }
                        }
                    }
                }
            }
        }
}