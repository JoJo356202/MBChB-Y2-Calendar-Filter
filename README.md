[README.md](https://github.com/user-attachments/files/25112771/README.md)
# AI-generated MBChB Year 2 Calendar Filter

A web-based tool for the University of Auckland MBChB Year 2 students to filter their calendar based on group numbers.

## Overview

This AI-generated tool helps you create a personalised calendar by filtering out group-specific events that don't apply to you. It processes ICS calendar files and keeps only the events relevant to your assigned groups, as well as all general lectures and events.

## **DISCLAIMER**

⚠️ **USE AT YOUR OWN RISK**

- This tool is provided as-is with **no guarantee of 100% accuracy**
- Always **double-check** the filtered calendar against your original
- **Review the removed events list** carefully before relying on the filtered calendar
- The tool may not catch all edge cases or unusual formatting
- The downloaded ICS file from the timetable website does include classes that do not show up on the timetable on the website
- This is a student-made tool and is not officially affiliated with or endorsed by the University of Auckland

## Features

- ✅ Filter events by **SGA Group** (1-24)
- ✅ Filter events by **HAL Lab Table** (1A-15A, 1B-15B)
- ✅ Filter events by **Nutrition Lab Group** (1-7)
- ✅ Automatically keeps all general lectures and non-group-specific events
- ✅ Visual summary panel showing all removed events for verification
- ✅ Optional: Split calendar into separate category files
- ✅ Works entirely in your browser - no data uploaded to any server

## How to Use

### Step 1: Get Your Calendar File

1. Export your MBChB Year 2 calendar as an ICS file
2. Save it somewhere you can easily find it

### Step 2: Open the Tool

1. Download `ics-filter.html` from this repository
2. Open it in any modern web browser (Chrome, Firefox, Safari, Edge)

### Step 3: Upload Your Calendar

1. Click the **"Upload ICS File"** button
2. Select your downloaded calendar file

### Step 4: Enter Your Groups

Enter your assigned group numbers for each category:

- **SGA Group**: Enter a number from 1-24 (e.g., `7`, `15`)
- **HAL Lab Table**: Enter your table assignment with letter (e.g., `3A`, `10B`, `15A`)
- **Nutrition Lab Group**: Enter a number from 1-7 (e.g., `2`, `5`)

**Important Notes:**
- HAL Lab has separate A and B classes - make sure you enter the correct letter
- All three fields are required

### Step 5: Preview Your Filtered Calendar

1. Click the **"Preview Filtered Calendar"** button
2. A summary panel will appear on the right side showing:
   - Total events that will be kept
   - Total events that will be removed
   - **Complete list of all removed events** for you to review

### Step 6: Review and Restore Events

**CRITICAL STEP**: Always review the removed events list!

The summary panel shows every event that was filtered out. For each removed event:
- Review the event title to confirm it should be removed
- If an event was incorrectly removed, click the **"Add"** button next to it to restore it
- Restored events will be crossed out and marked with a ✓
- The event count in the download button updates automatically

**If you see any events that shouldn't have been removed**, click the "Add" button to restore them!

# Step 7: Choose Your Download Option

In the summary panel at the top, you have two options:

#### Option A: Single Filtered Calendar (Default)

Leave the "Split into separate files by category" checkbox **unchecked**. This will create one filtered calendar with all your relevant events.

#### Option B: Split by Category

Check the **"Split into separate files by category"** box. This will download **separate ICS files** for each category:
- `lectures.ics` - All lecture events
- `hal_labs.ics` - HAL Lab events for your table
- `sga_groups.ics` - SGA Group events for your group
- `nutrition_groups.ics` - Nutrition Lab events for your group
- `tests.ics` - All tests, exams, quizzes
- `deadlines.ics` - All deadlines and assignments
- `other.ics` - Other miscellaneous events

This allows you to import different event types into different calendar apps or color-code them differently.

### Step 8: Download Your Calendar

1. Click the **"⬇️ Download Filtered Calendar"** button at the top of the summary panel
2. Your filtered calendar file(s) will automatically download
3. The download button shows the total number of events (including any restored events)

### Step 9: Import to Your Calendar App

1. Open your calendar application (Google Calendar, Outlook, Apple Calendar, etc.)
2. Import the downloaded ICS file(s)
3. Double-check your events against your original calendar to verify accuracy

## How It Works

The tool uses pattern matching to identify group-specific events:

### Event Filtering Logic

**Events ARE KEPT if:**
- They don't mention any group numbers (lectures, general events)
- They mention groups and YOUR group falls within the specified range

**Events ARE REMOVED if:**
- They mention groups and your group does NOT fall within the range

### Examples

If you're in:
- SGA Group: 7
- HAL Lab Table: 5A
- Nutrition Lab Group: 3

**Kept Events:**
- "Introduction to Pathology Lecture" ✅ (no groups mentioned)
- "Lab Session - SGA Group: 5-10" ✅ (you're in group 7, which is in range 5-10)
- "221 Tbl 3A-8A: Lab Skills" ✅ (you're in 5A, which is in range 3A-8A)
- "Nutrition Group: 1-4 Session" ✅ (you're in group 3, which is in range 1-4)

**Removed Events:**
- "Lab Session - SGA Group: 15-20" ❌ (you're not in range 15-20)
- "221 Tbl 1B-10B: Lab Skills" ❌ (you're in A class, not B class)
- "Nutrition Group: 5-7 Session" ❌ (you're not in range 5-7)

## Supported Event Title Formats

The tool recognises these patterns in event titles:

- **SGA**: "SGA Group: 5-10", "SGA: 5-10", "SGA Group: 7"
- **HAL Lab**: "HAL Lab Group: 3A-8A", "HAL: 5B-10B", "Tbl 1A-5A"
- **Nutrition**: "Nutrition Group: 2-5", "Nutrition: 3-6"

## Troubleshooting

### "Error processing file"
- Make sure you uploaded a valid ICS file
- Check that you filled in all three group fields
- Try re-exporting your calendar and uploading again

### Events I need are being removed
- Check that you entered your group numbers correctly
- Verify your group assignments are accurate
- Review the event title format - the tool may not recognize unusual formats
- **Use the "Add" button to restore any incorrectly removed events**

### Events I don't need are being kept
- The tool keeps all events that don't mention specific groups
- If an event should have a group but doesn't, it will be kept
- You may need to manually remove these from your calendar app after importing

### HAL Lab filtering isn't working correctly
- Make sure you include the letter (A or B) in your table number
- Remember A and B classes are completely separate (5A ≠ 5B)
- Check the removed events list to verify correct filtering
- For events with multiple ranges (e.g., "Tbl 1A-5A & Tbl 1B-5B"), make sure at least one range matches your group

### Restore button not working
- Make sure you've clicked "Preview Filtered Calendar" first
- The "Add" button should change to "✓" when clicked
- Check that the event count in the download button updates
- Try refreshing the page and starting over if issues persist

### Split files option not working
- Make sure you check the "Split into separate files" box in the summary panel (not the main panel)
- The checkbox appears after you preview the filtered calendar

## Technical Details

- Pure HTML/CSS/JavaScript - runs entirely in your browser
- No server-side processing - your calendar data never leaves your device
- Compatible with all modern web browsers
- File processing happens locally for privacy

## Contributing

Found a bug or have a suggestion? Feel free to:
- Open an issue
- Submit a pull request
- Share feedback with other MBChB Y2 students

## Version History

### v1.0
- Initial release
- Support for SGA, HAL Lab, and Nutrition group filtering
- Events summary panel
- Category splitting option

### v1.1
- Fixed issue with missing class
- Restore button to add back incorrectly removed events

---

*Always verify filtered calendars against official sources. When in doubt, refer to your original calendar*
