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
            steps {
                build 'etlJobCalcStockCompositeScore'
                build 'etlJobCalcSSGComposite'
                build 'etlJobCalcStockBuySellSpotsDynamic'
                build 'etlJobCalcStockActionCategoryFeatureGen'
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
        stage('etlJobMLStockDatafileDownloader'){
            steps {
                build 'etlJobMLStockDatafileDownloader'
            }
        }
        stage('DAILY_MODEL_RUN'){
            steps {
                build 'etlJobMLStockPerformanceModelDaily_DAILY_MODEL_RUN_10DAY'
                build 'etlJobMLStockPerformanceModelDaily_DAILY_MODEL_RUN_5DAY'
                build 'etlJobMLStockPerformanceModelDaily_DAILY_MODEL_RUN_10DAY_GEMINI'
                build 'etlJobScriptWrapper_tensorflow_healthcare'
            }
        }
        stage('DAILY_STOCK_PREDICTION_BACKFILL'){
            steps {
                build 'etlJobMLDataStockPredictionActualBackfill_DAILY_STOCK_PREDICTION_BACKFILL_10DAY'
                build 'etlJobMLDataStockPredictionActualBackfill_DAILY_STOCK_PREDICTION_BACKFILL_5DAY'
            }
        }
        stage('etlJobScriptWrapper_ml_daily_market_cap_patch'){
            steps{
                build 'etlJobScriptWrapper_ml_daily_market_cap_patch'
            }
        }
        stage('DAILY_STOCK_PREDICTION_EXPORT'){
            steps {
                build 'etlJobMLDataStockPredictionExport_DAILY_STOCK_PREDICTION_EXPORT_10DAY'
                build 'etlJobMLDataStockPredictionExport_DAILY_STOCK_PREDICTION_EXPORT_5DAY'
                build 'etlJobMLDataStockPredictionExport_DAILY_STOCK_PREDICTION_EXPORT_10DAY_GEMINI'
            }
        }
        stage('DAILY_WATERFALL_EXPORT'){
            steps {
                build 'etlJobMLDataStockPredictionWaterfallExport_DAILY_WATERFALL_EXPORT_10DAY'
                build 'etlJobMLDataStockPredictionWaterfallExport_DAILY_WATERFALL_EXPORT_5DAY'
            }
        }
        stage('DAILY_DIAGNOSTICS'){
            steps {
                build 'etlJobMLDataStockPredictionDiagnostics_DAILY_DIAGNOSTICS_10DAY'
                build 'etlJobMLDataStockPredictionDiagnostics_DAILY_DIAGNOSTICS_5DAY'
            }
        }
        stage('ORLIN Universes'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_ORLIN_UNIVERSE1', propagate: false
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_ORLIN_UNIVERSE2', propagate: false
                build 'etlJobMLDataStockPredictionExportCustomerOrlinSPY', propagate: false
            }
        }
        stage('ORLIN Entry and Exit'){
            steps {
                build 'etlJobMLDataStockPredictionOrlinEntryGen', propagate: false
                build 'etlJobMLDataStockPredictionOrlinExitGen', propagate: false
            }
        }
        stage('Orlin MIDDY Signal Gen'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_ORLINMIDDY', propagate: false
            }
        }
        stage('Orlin MIDDY Entry / Exit Gen'){
            steps {
                build 'etlJobMLDataStockPredictionOrlinEntryGenMIDDY', propagate: false
                build 'etlJobMLDataStockPredictionOrlinExitGenMIDDY', propagate: false
            }
        }
        stage('etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_JIM_PP'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_JIM_UNIVERSE1'
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_JIM_UNIVERSE2'
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_JIM_KELLY'
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_PRESPOINT_UNIVERSE1'
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_PRESPOINT_UNIVERSE2'
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_PRESPOINT_KELLY'
            }
        }
        stage('etlJobMLSendStockPredictionEmail'){
            steps {
                build 'etlJobMLSendStockPredictionEmail'
            }
        }
        stage('etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_LAZARD'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_LAZARDLIQUID'
                build 'etlJobMLDataStockPredictionExportCustomer_DAILY_STOCK_PREDICTION_EXPORT_10DAY_LAZARDMIDDY'
            }
        }
        stage('etlJobMLDataStockPredictionExportCustomerTP_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE1'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerTP_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE1'
            }
        }
        stage('etlJobMLDataStockPredictionExportCustomerTP_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE2'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerTP_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE2'
            }
        }
        stage('etlJobMLDataStockPredictionExportCustomerTP_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE3'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerTP_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE3'
            }
        }
        stage('etlJobMLDataStockPredictionExportCustomerTPAggregate_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE_AGGREGATE'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerTPAggregate_DAILY_STOCK_PREDICTION_EXPORT_10DAY_TIDEPOINT_UNIVERSE_AGGREGATE'
            }
        }
        stage('Single Universe Customer Exports'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerHealthcor'
                build 'etlJobMLDataStockPredictionExportCustomerBarclaysLarge'
                build 'etlJobMLDataStockPredictionExportCustomerBarclaysMIDDY'
            }
        }
        stage('Generate Signal Exports'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerOrlinHealthcare1', propagate:false
                build 'etlJobMLDataStockPredictionExportCustomerOrlinHealthcare2', propagate:false
            }
        }
        stage('Generate Entry and Exit Files'){
            steps {
                build 'etlJobMLDataStockPredictionOrlinEntryGenHealthcare', propagate:false
                build 'etlJobMLDataStockPredictionOrlinExitGenHealthcare', propagate:false
            }
        }
        stage('SR Daily ML Data Asymmetry'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerAsymmetryTheraOnly', propagate:false
                build 'etlJobMLDataStockPredictionExportCustomerAsymmetryNonThera', propagate:false
            }
        }
        stage('etlJobMLDataStockPredictionAsymmetryAggregator'){
            steps{
                build 'etlJobMLDataStockPredictionAsymmetryAggregator', propagate:false
            }
        }
        stage('Signal Exports'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerJPMorgan', propagate:false
                build 'etlJobMLDataStockPredictionExportCustomerJPMorganLarge', propagate:false
                build 'etlJobMLDataStockPredictionExportCustomerJPMorganMIDDY', propagate:false
            }
        }
        stage('Summary Matrix Exports'){
            steps {
                build 'etlJobMLDataPivotRun_JPMORGAN_LARGECAP', propagate:false
                build 'etlJobMLDataPivotRun_JPMORGAN_UNIVERSE', propagate:false
                build 'etlJobMLDataPivotRun_JPMORGAN_MIDDY', propagate:false
            }
        }
        stage('Orbimed'){
            steps {
                build 'etlJobMLDataStockPredictionExportCustomerOrbimed', propagate:false
                build 'etlJobMLDataStockPredictionExportCustomerOrbimedThera', propagate:false
                build 'etlJobMLDataStockPredictionExportCustomerOrbimedNonThera', propagate:false
            }
        }
        stage('Orlin Aggregator'){
            steps {
                build 'etlJobMLDataStockPredictionOrlinEntryAggregator', propagate:false
                build 'etlJobMLDataStockPredictionOrlinExitAggregator', propagate:false
            }
        }
        stage('Post Customer Exports update actuales'){
            steps {
                build 'etlJobScriptWrapper_ml_daily_update_export_actuals', propagate:false
            }
        }
        stage('Customer Diagnostics'){
            steps {
                build 'etlJobMLDataStockPredictionDiagnostics_DIAGNOSTICS_LAZARDI50TO100B', propagate:false
            }
        }
        stage('Post Customer Exports'){
            steps {
                build 'etlJobMLDataStockPredictionPNLExport', propagate:false
            }
        }
        stage('File Pump'){
            steps {
                build 'etlJobCustomerFilePump', propagate:false
            }
        }
        stage('etlJobScriptWrapper_ml_daily_phase3'){
            steps {
                build 'etlJobScriptWrapper_ml_daily_phase3'
            }
        }
        stage('etlJobMLDataSSGExport'){
            steps {
                build 'etlJobMLDataSSGExport'
            }
        }
        stage('etlJobScriptWrapper_tensorflow_regimevision'){
            steps {
                build 'etlJobScriptWrapper_tensorflow_regimevision'
            }
        }
        stage('etlJobMLDataSSGProbabilityUpdate'){
            steps {
                build 'etlJobMLDataSSGProbabilityUpdate'
            }
        }
        stage('etlJobMLRegimeVisionKelly'){
            steps {
                build 'etlJobMLRegimeVisionKelly'
            }
        }
        stage('etlJobMLDataRegimeVisionSkew'){
            steps {
                build 'etlJobMLDataRegimeVisionSkew'
            }
        }
        stage('etlJobExecuteSQLFile_update_rv_ssg_ml_anlysis'){
            steps {
                build 'etlJobExecuteSQLFile_update_rv_ssg_ml_anlysis'
            }
        }
        stage('etlJobWebCacheUpdate'){
            steps {
                build 'etlJobWebCacheUpdate'
            }
        }
        stage('etlJobCustomerFileRetriever'){
            steps {
                build 'etlJobCustomerFileRetriever'
            }
        }
        stage('csvLoaderPortfolioImport'){
            steps {
                build 'csvLoaderPortfolioImport'
            }
        }
        stage('Change Summary and Portfolio Scoring'){
            steps {
                build 'etlJobChangeSummary'
                build 'etlJobCalcPortfolioScoreParallel'
            }
        }
        stage('etlJobCalcBenchmarkScore'){
            steps {
                build 'etlJobCalcBenchmarkScore'
            }
        }
        stage('etlJobCalcPortfolioDailyPDFGenQueuePublisher'){
            steps {
                build 'etlJobCalcPortfolioDailyPDFGenQueuePublisher'
            }
        }
        stage('etlJobPortfolioAlphaSignalCSVExport'){
            steps {
                build 'etlJobPortfolioAlphaSignalCSVExport'
            }
        }
        stage('etlJobBenchmarkAlphaSignalCSVExport'){
            steps {
                build 'etlJobBenchmarkAlphaSignalCSVExport'
            }
        }
        stage('etlJobSendPortfolioDailyEmail'){
            steps {
                build 'etlJobSendPortfolioDailyEmail'
            }
        }
        stage('etlJobSendWatchlistAlertEmail'){
            steps {
                build 'etlJobSendWatchlistAlertEmail'
            }
        }
        stage('etlJobPortfolioSummaryExport'){
            steps {
                build 'etlJobPortfolioSummaryExport'
            }
        }
        stage('etlJobPortfolioCSVExport'){
            steps {
                build 'etlJobPortfolioCSVExport'
            }
        }
        stage('etlJobCustomerFilePump'){
            steps {
                build 'etlJobCustomerFilePump'
            }
        }
    }
}