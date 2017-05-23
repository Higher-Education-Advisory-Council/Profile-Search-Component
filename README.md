# Profile-Search-Component

This is a group of Lightning Components built for Salesforce Communities that uses SOSL (or SOQL optionally) to search the User records for keywords. It is built in the same style as the People Search in Chatter

It is built with four components:

1) The search bar (searchBar.cmp) - this has a text box that collects the search term. 
2) The application event (SearchKeyChange.evt) is called by the searchBar component on the onkeyup event
3) The people list (PeopleList.cmp) accesses the search term from the applciation event and displays a list of matching users.
4) The community component (QuickPeople.cmp) brings everything together and has a design component where you can choose the type of search.

The apex controller (DisplayUserController.apxc) performs the SOQL/SOSL query against the users that have access to the community its running in. In order to do that, it finds:

1) The NetworkID of the current community from the Network object
2) Using the NetworkID from above, it creates a list of users that have access to the community from the NetworkMember object. That list is used in the SOSL/SOQL query as a search filter.
