## Includes the following ##
source:
Compo-Pack
https://7daystodie.com/forums/showthread.php?28057-Compo-Pack-for-Random-Gen

Simple UI Plus
http://www.nexusmods.com/7daystodie/mods/70/?

SurvivalMod 1.6 (with Merged changes from Simple UI Plus)
http://www.nexusmods.com/7daystodie/mods/64/?tab=4&&navtag=http%3A%2F%2Fwww.nexusmods.com%2F7daystodie%2Fajax%2Fcomments%2F%3Fmod_id%3D64%26page%3D1%26sort%3DDESC%26pid%3D0%26thread_id%3D5776607&pUp=1
Simple UI Plus Modification:
	Config/loot.xml changes:
		<lootcontainer id="10" count="0" size="8,9" sound_open="UseActions/open_chest" sound_close="UseActions/close_chest" loot_quality_template="baseTemplate">
		-->	
			<lootcontainer id="10" count="0" size="14,13" sound_open="UseActions/open_chest" sound_close="UseActions/close_chest" loot_quality_template="baseTemplate">
		
		<lootcontainer id="41" count="0" size="5,10" destroy_on_close="true" sound_open="UseActions/open_backpack" sound_close="UseActions/close_backpack" open_time="1" loot_quality_template="baseTemplate">
		-->	
			<lootcontainer id="41" count="0" size="10,14" destroy_on_close="true" sound_open="UseActions/open_backpack" sound_close="UseActions/close_backpack" open_time="1" loot_quality_template="baseTemplate">
		
		<lootcontainer id="62" count="0" size="3,6" sound_open="UseActions/open_shopping_basket" open_time="0" sound_close="UseActions/close_shopping_basket" loot_quality_template="baseTemplate">
		-->	
			<lootcontainer id="62" count="0" size="12,15" sound_open="UseActions/open_shopping_basket" open_time="0" sound_close="UseActions/close_shopping_basket" loot_quality_template="baseTemplate">
	
	Config/xui.xml
		<ruleset name="default" scale="1.255" stackpanel_scale="1.05">
		-->	
			<ruleset name="default" scale="1.05" stackpanel_scale="0.94">
		
		<window name="windowForgeInput" />
		-->	
			<window name="S420windowForgeInput" />
		
		<window name="windowLooting"/>
		-->	
			<window name="S420windowLooting"/>
		
		<window name="windowCompass" />
		-->	
			<window name="S420windowCompass" />
			<window name="S420ActiveBuffsWindow" anchor="LeftBottom" /> <!-- buff timers - placed here so it disappears when compass does -->
			<window name="S420windowQuestTracker" anchor="RightTop" /> <!-- placed here so it disappears when compass does -->
			
			<window_group name="toolbelt" actionSet="false">
				<window name="windowToolbelt" anchor="CenterBottom" />
				<window name="HUDLeftStatBars" anchor="LeftBottom" />
				<window name="HUDRightStatBars" anchor="RightBottom" />
				<window name="windowQuestTracker" anchor="RightTop" />
			</window_group>
			
			<window_group name="vehicle" controller="XUiC_VehicleWindowGroup">
				<window name="windowVehicle"/>
				<window name="windowNonPagingHeader" />
				<window name="windowVehicleStats" />
				<window name="windowVehicleStorage" />
			</window_group>
			<window_group name="toolbelt" actionSet="false">
	<!-- S420 Start -->
				<window name="S420XpBar" anchor="CenterBottom" />
				<!--window name="windowToolbelt" anchor="CenterBottom" /--> <!--Stock-->
				<window name="S420windowToolbelt" anchor="CenterBottom" />
				<!--window name="HUDLeftStatBars" anchor="LeftBottom" /--> <!--Stock-->
				<window name="S420HUDLeftStatBars" anchor="LeftBottom" />
				<!--window name="S420BuffPopoutList" anchor="LeftBottom" /--> <!-- stock like buff list -->
				<window name="HUDRightStatBars" anchor="RightBottom" />
				<!--window name="windowQuestTracker" anchor="RightTop" /--> <!--Stock-->
	<!-- S420 End -->
			</window_group>
		
			<window_group name="vehicle" controller="XUiC_VehicleWindowGroup">
	<!-- S420 Start -->
				<!--window name="windowVehicle"/--> <!--Stock-->
				<window name="S420windowVehicle"/>
				<!--window name="windowNonPagingHeader" /--> <!--Stock-->
				<window name="S420windowNonPagingHeaderLeft" />
				<!--window name="windowVehicleStats" /--> <!--Stock-->
				<window name="S420windowVehicleStats" />
				<!--window name="windowVehicleStorage" /--> <!--Stock-->
				<window name="S420windowVehicleStorage" />
	<!-- S420 End -->
			</window_group>

	Config/XUI/controls.xml		
		Added the following to the top of hte file:
		
			<!-- S420 Start -->
		<S420_item_stack>
			<rect controller="ItemStack" style="S420itemStack, hover" collider_scale="1.1">
				<sprite depth="2" name="backgroundMain" sprite="menu_empty3px" pos="-3,3" width="88" height="88" color="[transparent]" type="sliced" fillcenter="false" />	
				<sprite depth="3" name="background" sprite="menu_empty3px" width="83" height="83" color="[darkGrey]" type="sliced" globalopacity="true" fillcenter="false"/>
				<sprite depth="2" name="highlightOverlay" width="82" height="82" color="[darkGrey]" pos="0,0" type="sliced" globalopacity="true" visible="false"/>

				<sprite depth="3" name="backgroundTexture" size="83,83" color="[black_half_alpha]" type="sliced" />
				
				<sprite depth="4" name="itemIcon" width="76" height="56" atlas="ItemIconAtlas" sprite="{itemicon}" pos="42,-35" pivot="center" foregroundlayer="true" color="{iconcolor}" />
				<sprite depth="8" name="lockTypeIcon" width="24" height="24" sprite="" pos="2,-2" foregroundlayer="true"/>
				
				<sprite depth="3" name="durabilityBackground" width="75" height="10" sprite="menu_empty3px" color="[darkGrey]" type="sliced" pos="4, -70" foregroundlayer="true"/>
				<sprite depth="4" name="durability" width="75" height="10" sprite="menu_empty2px" color="[transparent]" type="filled" pos="4, -70" foregroundlayer="true"/>
				
				<sprite depth="5" name="disabledOverlay" width="82" height="82" color="[darkGrey_half_alpha]" pos="1,-1" type="sliced" visible="false"/>
				
				<label depth="7" name="stackValue" pos="5,-54" width="70" height="28" text="{itemcount}" font_size="26" effect="outline" justify="center" />
				<label depth="7" name="timer" pos="35,-38" width="70" height="24" font_size="24" justify="center" pivot="center" effect="outline" color="[beige]"/>
				<sprite depth="9" name="cancel" sprite="ui_game_symbol_x" width="70" height="70" color="255,0,0,255" type="sliced" visible="false" foregroundlayer="true"/>
				<label depth="12" name="itemName" pos="36,-35" width="0" height="0" text="" font_size="26" justify="center" overflow="resizefreely" effect="outline" pivot="center" above_soft_cursor="true"/>
				<sprite depth="13" name="assembleIcon" size="40,40" sprite="ui_game_symbol_lock" visible="{isassemblelocked}" pos="14,-14" foregroundlayer="true" />
			</rect>
		</S420_item_stack>

		<S420_quest_objective_tracker_entry>
			<rect width="300" height="26" controller="QuestTrackerObjectiveEntry" visible="{hasobjective}" >
				
				<sprite depth="2" name="iconTrack" style="icon22px" pos="280,0" color="{objectivecompletecolor}" sprite="{objectivecompletesprite}" visible="{objectiveshowicon}" />
				
				<label depth="1" pos="0,4" text="{objectiveoptional}{objectivedescription} [{objectivecompletehexcolor}]{objectivestate}[-]" upper_case="true" font_size="26" justify="right" visible="{hasobjective}" width="{objectivetextwidth}" effect="outline" />
			</rect>
		</S420_quest_objective_tracker_entry>

		<S420_vehicle_part_slot>
			<rect controller="VehiclePartStack" style="S420vehicleStack, hover" >
				<sprite depth="2" name="backgroundMain" sprite="menu_empty3px" pos="-3,3" width="350" height="50" color="[black]" type="sliced" fillcenter="false" />	
				<sprite name="background" color="[darkGrey]" height="46" pos="0,1" type="sliced"/>
				<label depth="4" pos="14,-8" width="250" height="28" text="{partname}" font_size="26" justify="left" />
				<label depth="4" pos="228,-8" width="50" height="28" text="{partquality}" font_size="26" justify="right" />
				
				<sprite depth="2" width="255" pos="15,-35" height="10" type="sliced" color="[black]" visible="{partvisible}" foregroundlayer="true" />
				<sprite depth="2" width="253" pos="16,-36" height="8" type="sliced" color="[mediumGrey]" visible="{partvisible}" foregroundlayer="true" />
				<sprite depth="2" name="sprFill" width="253" pos="16,-36" height="8" type="filled" color="{partcolor}" fill="{partfill}" visible="{partvisible}" foregroundlayer="true" />
				
				<sprite name="itemIcon" depth="4" width="50" height="40" atlas="{partatlas}" sprite="{particon}" pos="311,-26" pivot="center" color="{particoncolor}" foregroundlayer="true" />
			</rect>
		</S420_vehicle_part_slot>
	<!-- S420 End -->
		
	Config/XUI/styles.xml		
		Added the following to the top of hte file:		
		
			<!-- S420 Start-->
		<style name="S420itemStack">
			<style_entry name="select_color" value="[beige]"/>
			<style_entry name="press_color" value="[limeGreen]"/>
			<style_entry name="final_pressed_color" value="[lightGrey]"/>
			<style_entry name="background_color" value="[mediumGrey]"/>
			<style_entry name="highlight_color" value="[hoverColor]"/>
			<style_entry name="holding_color" value="[green]"/>
			<style_entry name="width" value="82"/>
			<style_entry name="height" value="82"/>
			<style_entry name="hover_icon_grow" value="1.5"/>
			<style_entry name="on_press" value="true"/>
			<style_entry name="sound_volume" value="0.75"/>
			<style_entry name="pickup_sound" value="[pickup_click]"/>
			<style_entry name="place_sound" value="[place_click]"/>
		</style>

		<style name="S420vehicleStack">
			<style_entry name="background_color" value="[darkGrey]"/>
			<style_entry name="highlight_color" value="[lightGrey]"/>
			<style_entry name="width" value="344"/>
			<style_entry name="height" value="48"/>
			<style_entry name="hover_icon_grow" value="1.5"/>
			<style_entry name="on_press" value="true"/>
			<style_entry name="sound_volume" value="0.75"/>
			<style_entry name="pickup_sound" value="[pickup_click]"/>
			<style_entry name="place_sound" value="[place_click]"/>
		</style>

		<style type="sprite" name="icon26px">
			<style_entry name="color" value="[iconColor]"/>
			<style_entry name="width" value="26"/>
			<style_entry name="height" value="26"/>
			<style_entry name="foregroundlayer" value="true" />
		</style>
	<!-- S420 End -->

	Config/XUI/styles.xml		
		munged it as best I could	
	

Valmar's Animal Snares
https://7daystodie.com/forums/showthread.php?31668-Animal-Snares

Valmar's Survival Notes
https://7daystodie.com/forums/showthread.php?30751-Survivor-Notes-Experience-and-Recipe-Books

Valmar's Reusable Cooking Bowls
https://7daystodie.com/forums/showthread.php?27592-MOD-Reusable-Cooking-Bowls

Valmar's Working Electric Lights
https://7daystodie.com/forums/showthread.php?34748-Working-Electric-Lights

Valmar's Expanded Player Storage
https://7daystodie.com/forums/showthread.php?28211-Expanded-Player-Storage

Increased backpack survival time on death to 6 hours