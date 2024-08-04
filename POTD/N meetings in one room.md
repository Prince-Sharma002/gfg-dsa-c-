```
    // be performed in a meeting room.
int maxMeetings(int n, int start[], int end[]) {
    // Create a vector of pairs to store start and end times together
    vector<pair<int, int>> meetings;
    for (int i = 0; i < n; i++) {
        meetings.push_back({end[i], start[i]});
    }

    // Sort meetings based on their end times
    sort(meetings.begin(), meetings.end());

    // Initialize the count of meetings and the end time of the last attended meeting
    int count = 1;
    int lastEndTime = meetings[0].first;

    // Iterate through the sorted meetings
    for (int i = 1; i < n; i++) {
        // If the start time of the current meeting is after the end time of the last meeting
        if (meetings[i].second > lastEndTime) {
            count++;
            lastEndTime = meetings[i].first;
        }
    }

    return count;
}
```
