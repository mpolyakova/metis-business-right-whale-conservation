# An App to Save the North Atlantic Right Whale

## Abstract   
The North Atlantic Right Whale is a gentle giant who, quite matching his name, lives in the shallows along the Atlantic shoreline. These areas are an important shipping hub, causing a direct conflict with the whales.
The population of North Atlantic Right Whales is below 400 whales in the world, and still decreasing, despite speed restrictions and fishing regulation. In the last 5 years, we've lost 34 whales. A decrease in calves born, as well as whale deaths from vessel strikes and entanglement means the population is unlikely to recover without more help.

NOAA requires a new solution to protect the whales from vessel strikes. Ships avoid each other by radar and AIS, and the whales need that too. Our hypothesis is that alerting ships by chartplotter/phone/beacon of a nearby whale will decrease vessel strikes, and help the population recover. 

Sheets work: [Right Whale Protection sheet](https://docs.google.com/spreadsheets/d/1iZnwUQxNIA9MvONgjvyoW4_hprS16gVW8NYD126Elfs/edit?usp=sharing)
Tableau: [Right Whale Conservation](https://public.tableau.com/views/RightWhaleConservation/RightWhaleLifestyle?:language=en-US&:display_count=n&:origin=viz_share_link)
Presentation: [Slides](https://github.com/mpolyakova/metis-business-right-whale-conservation/blob/master/presentation%20NOAA%20Right%20Whale%20Conservation.pdf)

## Design
Given that speed regulation over certain areas did not decrease the number of vessel strike caused whale deaths, blanket area solutions do not appear to be effective. We need to hone in on specific whales and specific ships, the same way a radar does for ships, and interact with the ships directly to bring them relevant information. The ships location is always known from their beacon. Impact: By being able to say whether a whale is nearby, we can reach out to ships directly indicating a whale in their path. Since  sea regulations state that no ship can pass within 500 feet of a Right Whale, the ship must search and avoid the whale, therefore preventing a vessel strike. 

### Data Science Solution Path
* Classification model to predict whether a whale is in a nearby area. Using historical data, current water surface conditions (available via buoys in near real time), and recent observation data, we can create a binary classifier which when prompted replies yes/no to indicate whether a whale is nearby. Nearby can be defined in 2 ways: nearby any ships in relevant waters, or create a grid and predict whether a whale is in the grid, creating a sort of ocean heat map. The preferable way depends on model speed and density of shipping. NOAA, Coast Guard, and other relevant organizations can run the model and ping ships nearby automatically. 
* Future: Research on identifying whale noises underwater and pinpointing location is already taking place. Sensors can be placed on buoys, providing real time data without requiring human intervention, and supplementing both alerting and modeling. We could augment the alert to fire immediately to ships in visinity in response to this signal, and use it in the model and retraining. In a very future state, these sensors could be placed on ships, providing them their own whale radar. 

### Measures of Success
* Fewer deadly vessel strikes a year than the year before until no deadly vessel strikes occur.
* Proportionally fewer observational reports indicating fresh blunt force wounds on Right Whales (proportion of blunt force wounds to overall number of observations should decrease)
* Whale Population growth


### Assumptions and Risks
#### Assumption 1
Whales will continue to behave as they did before
##### Risk 
Recent reports of thinning whales, and zooplankton may mean a change in the environment, and change in whale behavior, rendering our historical data no longer applicable. 

#### Assumption 2
Shipping companies and ship captains will be open to receiving and responding to alerts
##### Risk
If shipping is resistant to use this tool, its usefulness will be limited in preventing vessel strikes. It could still, however be used in investigations and observation to guide observers to the whale.


## Data 
The project used historical survey results on Right Whales, shipping lanes and fairways in US waters information, including geometry, and historic surface water temperatures in coastal cities. Because shipping lanes are rather small, and after leaving them, the ships continue through the water, I pulled Traffic density data, and overlayed it with whale locations, however spatial file was too large to be uploaded to Tableau Public, and is represented via screenshots. 
Details, with links on data located in: [Overview Tab](https://docs.google.com/spreadsheets/d/1iZnwUQxNIA9MvONgjvyoW4_hprS16gVW8NYD126Elfs/edit?usp=sharing)


## Algorithms  
Python was used to filter the whale location data for only North Atlantic Right Whales. 
Excel was used to clean and combine data, flatten it, and add latitude and longitude. Details in [overview tab](https://docs.google.com/spreadsheets/d/1iZnwUQxNIA9MvONgjvyoW4_hprS16gVW8NYD126Elfs/edit?usp=sharing)
Excel was also used to pull some insights about shipping regulations and whales: Insights Shipping Regulations and Insights Whales tabs. 

Tableau was used to combine shipping data, whale locations, and temperature locations and visualize maps, movement over time, and density.

## Tools
Pandas and Jupyter notebook to filter data to Right Whales only
Excel to clean, aggregate, and enrich data
Tableau to explore and visualize findings and maps 
Powerpoint to communicate the hypothesis and proposal. 

## Communication
An overview sheet and two insights tabs in sheets [Sheet](https://docs.google.com/spreadsheets/d/1iZnwUQxNIA9MvONgjvyoW4_hprS16gVW8NYD126Elfs/edit?usp=sharing) describes data and provides background information and recent findings. 
A dashboard of findings is located in [Tableau Public](https://public.tableau.com/views/RightWhaleConservation/RightWhaleLifestyle?:language=en-US&:display_count=n&:origin=viz_share_link)
Powerpoint was used to deliver the pitch in a five minute presentation

