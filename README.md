# Hospital Appointment Attendance Analysis Using R

Student: Harshit Srinivasa Prasad  
Roll number: 160124771033

This project analyses appointment attendance and compares Random Forest and XGBoost. Predictions include attending and missing probabilities, with a separate follow-up flag selected using validation F1.

## Files

- `Hospital_Attendance_Presentation.pptx`: project presentation.
- `Hospital_Attendance_Report.html`: completed report with saved tables and graphs; open in a browser.
- `Hospital_Attendance_Report.Rmd`: standalone archived report source with embedded outputs; does not require report_data.rds.
- `new_patient_prediction.csv`: saved demonstration predictions.
- `KaggleV2-May-2016.csv.zip`: original hospital dataset.

## Rebuild the archived report

Use R with the rmarkdown package and Pandoc, then run:

```r
rmarkdown::render("Hospital_Attendance_Report.Rmd")
```

This preserves recorded outputs rather than rerunning model training. Install rmarkdown if required with `install.packages("rmarkdown")`.

## Reproducibility limits

The original dataset ZIP contains 110,527 appointments. The reported experiment used a working file with 53,978 appointments before cleaning and 53,976 after cleaning. The exact working subset and its selection procedure are not included here, so rerunning on the original ZIP may produce different results.

The training notebook must be added separately. This repository bundle currently documents the saved experiment; it does not supply a complete executable training pipeline or saved trained models.

The prediction CSV records a historical demonstration. Its patient inputs are not included in the CSV. An earlier notebook example used an invalid binary diabetes value; verify corrected inputs and replace the prediction output before treating it as a validated demonstration.

## Interpretation

The models estimate risk rather than guaranteeing attendance. Follow-up flags prioritise reminders and should not be used to cancel appointments automatically. Feature importance and attendance comparisons describe associations, not causes.
