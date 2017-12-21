# CalendarView
================

CalendarView
 
	dependencies {
	    compile 'com.henry:calendarview:1.1.2'
	}
 
DayPickerView


    <com.henry.calendarview.DayPickerView
        android:id="@+id/dpv_calendar"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:colorCurrentDay="@color/colorAccent"
        app:colorSelectedDayBackground="@color/colorAccent"
        app:colorSelectedDayText="@color/selected_day_text"
        app:colorPreviousDayText="#727272"
        app:colorNormalDayText="#727272"
        app:colorYearMonthText="#727272"
        app:colorWeekText="#727272"
        app:colorBusyDaysBg="#727272"
        app:colorInValidDaysBg="#727272"
        app:colorBusyDaysText="#FFFFFF"
        app:colorInValidDaysText="#FFFFFF"

        app:textSizeDay="14sp"
        app:textSizeTag="12sp"
        app:textSizeYearMonth="16sp"
        app:textSizeWeek="14sp"
        app:headerMonthHeight="50dp"
        app:selectedDayRadius="20dp"
        app:calendarHeight="320dp"
        app:enablePreviousDay="false"/>
         


DatePickerController

        DayPickerView.DataModel dataModel = new DayPickerView.DataModel();
        dataModel.yearStart = 2016;
        dataModel.monthStart = 6;
        dataModel.monthCount = 16;
        dataModel.defTag = "￥100";
        dataModel.leastDaysNum = 2;
        dataModel.mostDaysNum = 100;

		dayPickerView.setParameter(dataModel, new DatePickerController() {
            @Override
            public void onDayOfMonthSelected(SimpleMonthAdapter.CalendarDay calendarDay) {
                Toast.makeText(context, "onDayOfMonthSelected", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onDateRangeSelected(List<SimpleMonthAdapter.CalendarDay> selectedDays) {
                Toast.makeText(context, "onDateRangeSelected", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void alertSelectedFail(FailEven even) {
                Toast.makeText(context, "alertSelectedFail", Toast.LENGTH_SHORT).show();
            }
        });

onDayOfMonthSelected(SimpleMonthAdapter.CalendarDay calendarDay);          

onDateRangeSelected(List<SimpleMonthAdapter.CalendarDay> selectedDays);    

alertSelectedFail(FailEven even);										   

---

    <declare-styleable name="DayPickerView">
        <attr name="colorCurrentDay" format="color"/>               
        <attr name="colorSelectedDayBackground" format="color"/>    
        <attr name="colorSelectedDayText" format="color"/>          
        <attr name="colorPreviousDayText" format="color"/>          
        <attr name="colorNormalDayText" format="color" />           
        <attr name="colorYearMonthText" format="color" />          
        <attr name="colorWeekText" format="color" />                
        <attr name="colorBusyDaysBg" format="color" />              
        <attr name="colorInValidDaysBg" format="color" />           
        <attr name="colorBusyDaysText" format="color" />           
        <attr name="colorInValidDaysText" format="color" />         

        <attr name="textSizeDay" format="dimension"/>              
        <attr name="textSizeTag" format="dimension"/>              
        <attr name="textSizeYearMonth" format="dimension" />       
        <attr name="textSizeWeek" format="dimension" />             
        <attr name="headerMonthHeight" format="dimension" />       
        <attr name="selectedDayRadius" format="dimension" />       
        <attr name="calendarHeight" format="dimension" />          
        <attr name="enablePreviousDay" format="boolean" />         
	</declare-styleable>
