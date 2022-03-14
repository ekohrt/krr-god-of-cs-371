# krr-god-of-cs-371 (Aaron Cooper, Ethan Kohrt, Ziyu Wang, Stephanie Yaur)
# Evanston Activity Recommender

[Final report](https://docs.google.com/document/d/1fmkqiNBnColvEs_dlWXqnH4AWm6-HNjfcDnnUqNNlg4/edit?usp=sharing)

FILES
ActivitiesMt.krf (Evanston activities and their attributes)
UserInputsMt.krf (User preferences corresponding to the attributes in ActivitiesMt.krf)
ReasoningRulesMt.krf (Logic that matches activities and user preferences)
example-inputs-1.krf (An example user's preferences)
example-inputs-2.krf (Another example user's preferences)

WHAT
Our Evanston Activity Recommender will suggest activities for you based on your preferences. A user can specify whether they want an activity to be indoors/outdoors, on/off campus, whether they want food, alcohol, a place to study, and more. The system also makes sure that the activity is open or available at the current time. Some example activities include going for a walk on the lakefill, getting ice cream from Cold Stone, or browsing for a new book at Bookends & Beginnings.

HOW TO USE
1. First specify user preferences - use example-inputs-1.krf or example-inputs-2.krf as examples.
2. Then load ActivitiesMt.krf, ReasoningRulesMt.krf, UserInputsMt.krf, and your user preference file such as example-inputs-1.krf into companions.
3. Query (thingToDo ?activity)
You will end up with a list of activity recommendations.

BUILD ON THIS
To create more activities, go to ActivitiesMt.krf and refer to specified activities as examples. Activites in general should be defined as being on/off campus, indoors/outdoors, and what hours they are open. Then specific tags such as if they're study spots, serve food, etc should be added.
To create more activity classifiers, go to ActivitiesMt.krf and define predicates there. A good reference example would be studySpot, lines 71-75. Then use the predicate as applies to activities. Adding a new activity classifier would likely mean that this is something a user would say if they prefer or not, and so that would mean adding a new user predicate in UserInputsMt.krf. A good reference example would be wantsStudySpot, lines 73-77. Finally, to actually find activities that fit this user preference, a horn clause would needed to be added to ReasoningRulesMt.krf. A good reference example would be correctStudySpot, lines 81-93. Then the new "correct???" horn clause should be added to the overarching (thingToDo ?a) horn clause. That would just mean adding (correctNEWCLAUSE ?a) to line 209.


