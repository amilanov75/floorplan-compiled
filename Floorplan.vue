<!-- html section -->
<template lang="html">

   <!-- This is where the output from the Vue #app is displayed -->
    <b-container style="color: #c2c2c2;" >

    
    <!-- ****************** FLOORPLAN IMAGE ****************** -->
    <template>
        <div id="floorplan" style="position:relative; left: -272px; width: 1720px; top:66px; height:35em; background:url(../../src/images/groundfloor.PNG);">

            <div style="position:absolute; left:1490px; top:450px; color:#dbdbdb; font-size:85%;"> <p> Kitchen Landing </p></div>
            <div style="position:absolute; left:125px; top:450px; color:#dbdbdb; font-size:85%;"> <p> Garden Bath </p></div>

            <div style="position:absolute; left:1570px; top:255px; color:#dbdbdb; font-size:85%;"> <p> Kitchen WC </p></div>
            
            <div style="position:absolute; left:1425px; top:15px; color:#dbdbdb; font-size:85%;"> <p> Courtyard</p></div>
            <div style="position:absolute; left:1000px; top:15px; color:#dbdbdb; font-size:85%;"> <p> Kitchen</p></div>
            <div style="position:absolute; left:500px; top:15px; color:#dbdbdb; font-size:85%;"> <p> Garden</p></div>
            <div style="position:absolute; left:165px; top:15px; color:#dbdbdb; font-size:85%;"> <p> Garden Room</p></div>

            <!-- ****************** RELOAD PAGE BUTTON ****************** -->
            <div style="position:absolute; width:150px;  left:1550px; top:12px;" > <button style="color:grey; font-size:80% !important;" v-on:click="reloadPage()"> Reload Page </button></div> 

            <!-- ********************************************* KITCHEN LIGHTING SPOTS *************************************** -->
            <!-- ****************** LED SPOT LIGHTS ****************** Kit Cabinet -->
            <div style="position:absolute; left:var(--kitcabinet_left);                               top:360px; outline: none;" v-b-popover.click.blur.top="'Kitchen Cabinet 8x'" tabindex="0" >  <i v-on:click="clickLight('kitcabinet')" id="kitcabinet" class="fa fa-circle" aria-hidden="false" > </i></div>
            <div style="position:absolute; left:calc(var(--kitcabinet_left) + var(--value_adj));      top:357px"   class="light_brightness" > <animated-number :value="light_lookup_localname('kitcabinet').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitcabinet').brightness_hide"> </div>
            <!-- ****************** LED SPOT LIGHTS ****************** Kit Lounge-->
            <div style="position:absolute; left:1200px;  top:204px; outline: none;" v-b-popover.click.blur.top="'Kitchen Lounge 2x'" tabindex="0" >  <i v-on:click="clickLight('kitlounge')" id="kitlounge" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1224px;  top:204px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitlounge').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitlounge').brightness_hide">  </div>
            <!-- ****************** LED SPOT LIGHTS ****************** Kit Wall -->
            <div style="position:absolute; left:852px;  top:48px; outline: none;" v-b-popover.click.blur.top="'Kitchen Wall 5x'" tabindex="0" >  <i v-on:click="clickLight('kitwall')" id="kitwall" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:876px;  top:48px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitwall').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitwall').brightness_hide">  </div>
            <!-- ****************** LED SPOT LIGHTS ****************** Kit Pendant -->
            <div style="position:absolute; left:852px;  top:135px; outline: none;" v-b-popover.click.blur.top="'Kitchen Pendant'" tabindex="0" >  <i v-on:click="clickLight('kitpendant')" id="kitpendant" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:876px;  top:135px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitpendant').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitpendant').brightness_hide"> </div>
            <!-- ****************** LED SPOT LIGHTS ****************** Kit Island -->
            <div style="position:absolute; left:874px;  top:271px; outline: none;" v-b-popover.click.blur.top="'Kitchen Island 4x'" tabindex="0" >  <i v-on:click="clickLight('kitisland')" id="kitisland" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:898px;  top:268px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitisland').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitisland').brightness_hide">  </div>
            <!-- ****************** LED SPOT LIGHTS ****************** Kit Courtyard-->
            <div style="position:absolute; left:1420px;  top:62px; outline: none;" v-b-popover.click.blur.top="'Kitchen Courtywar 2x'" tabindex="0" >  <i v-on:click="clickLight('kitcourtyard')" id="kitcourtyard" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1444px;  top:62px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitcourtyard').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitcourtyard').brightness_hide">  </div>



            <!-- ********************************************* KITCHEN LIGHTING RGBW *************************************** -->
            <!-- ****************** RGBW LEDS *********************** Kit Skylight -->
            <div style="position:absolute; left:1310px; top:113px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kitchen Skylight RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitskyrgbw')" id="kitskyrgbw" class="skylight far fa-square" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1342px; top:114px"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitskyrgbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitskyrgbw').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Kit Edge/Ceiling -->
            <div style="position:absolute; left:1310px;  top:84px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kitchen Edge RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitedgergbw')" id="kitedgergbw" class="far fa-square" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1342px;  top:86px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitedgergbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitedgergbw').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Kit Sink -->
            <div style="position:absolute; left:874px;  top:407px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kitchen Sink RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitsinkrgbw')" id="kitsinkrgbw" class="fa fa-window-minimize" aria-hidden="false"></i></div>
            <div style="position:absolute; left:906px;  top:415px"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitsinkrgbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitsinkrgbw').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Kit Island -->
            <div style="position:absolute; left:970px;  top:246px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kitchen Island RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitislandrgbw')" id="kitislandrgbw" class="far fa-square" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1003px; top:249px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitislandrgbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitislandrgbw').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Kit Cabinet -->
            <div style="position:absolute; left:740px;  top:383px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kitchen Cabinet RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitcabinetrgbw')" id="kitcabinetrgbw" class="fa fa-window-minimize" aria-hidden="false"></i></div>
            <div style="position:absolute; left:772px;  top:391px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitcabinetrgbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitcabinetrgbw').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Kit Drinks Cabinet -->
            <div style="position:absolute; left:1095px;  top:383px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kitchen Drinks Cabinet'" tabindex="0" >  <i v-on:click="clickLight('kitdrinksrgbw')" id="kitdrinksrgbw" class="fa fa-window-minimize" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1127px;  top:391px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitdrinksrgbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitdrinksrgbw').brightness_hide">  </div>
            



            <!-- ********************************************* GARDEN LIGHTING *************************************** -->
            <!-- ****************** LED SPOT LIGHTS ****************** Garden Wall BBQ -->
            <div style="position:absolute; left:590px;  top:48px; outline: none;" v-b-popover.click.blur.top="'Garden Wall'" tabindex="0" >  <i v-on:click="clickLight('gardenwallbbq')" id="gardenwallbbq" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:614px;  top:48px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('gardenwallbbq').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('gardenwallbbq').brightness_hide">  </div>
            <!-- ****************** LED SPOT LIGHTS ****************** Garden Wall Bench -->
            <div style="position:absolute; left:590px;  top:413px; outline: none;" v-b-popover.click.blur.top="'Garden Wall'" tabindex="0" >  <i v-on:click="clickLight('gardenwallbench')" id="gardenwallbench" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:614px;  top:413px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('gardenwallbench').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('gardenwallbench').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Garden Bench -->
            <div style="position:absolute; left:500px;  top:403px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Garden Bench'" tabindex="0" >  <i v-on:click="clickLight('gardenbench')" id="gardenbench" class="fa fa-window-minimize" aria-hidden="false"></i></div>
            <div style="position:absolute; left:532px;  top:416px"    class="light_brightness" > <animated-number :value="light_lookup_localname('gardenbench').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('gardenbench').brightness_hide"> </div>



            <!-- ********************************************* GARDEN ROOM LIGHTING  *************************************** -->
            <!-- ****************** LED SPOT LIGHTS ****************** Garden Room Spots -->
            <div style="position:absolute; left:200px;  top:204px;; outline: none;" v-b-popover.click.blur.top="'Gardenroom Spots'" tabindex="0" >  <i v-on:click="clickLight('groomspot')" id="groomspot" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:224px;  top:204px"    class="light_brightness" > <animated-number :value="light_lookup_localname('groomspot').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('groomspot').brightness_hide">  </div>
            <div style="position:absolute; left:196px;  top:226px;"   class="zone_time_left" > {{zone_garden_room_time == "NaNs"? "" : zone_garden_room_time}} </div>
            <!-- ****************** RGBW LEDS *********************** Garden Room Edge -->
            <div style="position:absolute; left:125px;  top:46px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Gardenroom Edge'" tabindex="0" >  <i v-on:click="clickLight('groomedgergbw')" id="groomedgergbw" class="far fa-square" aria-hidden="false"></i></div>
            <div style="position:absolute; left:157px;  top:52px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('groomedgergbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('groomedgergbw').brightness_hide">  </div>


            <!-- ********************************************* GARDEN BATH LIGHTING *************************************** -->
            <!-- ****************** LED SPOT LIGHTS ****************** Garden Bath Spots -->
            <div style="position:absolute; left:139px;  top:400px; outline: none;" v-b-popover.click.blur.top="'Garden Bath Spots'" tabindex="0" >  <i v-on:click="clickLight('gbathspot')" id="gbathspot" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:163px;  top:400px;"   class="light_brightness" > <animated-number :value="light_lookup_localname('gbathspot').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('gbathspot').brightness_hide"> </div>
            <div style="position:absolute; left:103px;  top:402px;"   class="zone_time_left" > {{zone_garden_bath_time == "NaNs"? "" : zone_garden_bath_time}} </div>

            
            <!-- ****************** RGBW LEDS *********************** Garden Bath Edge -->
            <div style="position:absolute; left:187px;  top:397px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Garden Bath Edge'" tabindex="0" >  <i v-on:click="clickLight('gbathedgergbw')" id="gbathedgergbw" class="far fa-square" aria-hidden="false"></i></div>
            <div style="position:absolute; left:219px;  top:403px;"   class="light_brightness" > <animated-number :value="light_lookup_localname('gbathedgergbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('gbathedgergbw').brightness_hide">  </div>
            
            
                

            

            <!-- ********************************************* KITCHEN LANDING LIGHTING *************************************** -->
            <!-- ****************** LED SPOT LIGHTS ****************** Kitchen Corr Spots -->
            <div style="position:absolute; left:1460px;  top:335px; outline: none;" v-b-popover.click.blur.top="'Kit Corr Spots'" tabindex="0" >  <i v-on:click="clickLight('kitcorrspot')" id="kitcorrspot" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1484px;  top:332px;"    class="light_brightness " > <animated-number :value="light_lookup_localname('kitcorrspot').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitcorrspot').brightness_hide"></div>
            <div style="position:absolute; left:1458px;  top:357px;"    class="zone_time_left" > {{zone_kitchen_landing_time == "NaNs"? "" : zone_kitchen_landing_time}} </div>
            <!-- ****************** RGBW LEDS *********************** Kitchen Low RGBW -->
            <div style="position:absolute; left:1455px;  top:383px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kit Corr Low RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitcorrlowrgbw')" id="kitcorrlowrgbw" class="fa fa-window-minimize" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1487px;  top:396px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitcorrlowrgbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitcorrlowrgbw').brightness_hide">  </div>
            <!-- ****************** RGBW LEDS *********************** Kitchen Stairs RGB -->
            <div style="position:absolute; left:1543px;  top:282px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kit Stairs RGB'" tabindex="0" >  <i v-on:click="clickLight('kitcorrstairs')" id="kitcorrstairs" class="fa fa-window-minimize" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1575px;  top:293px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitcorrstairs').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitcorrstairs').brightness_hide"> </div>


            <!-- ********************************************* KITCHEN WC LIGHTING *************************************** -->
            <!-- ****************** LED SPOT LIGHTS ****************** Kitchen WC Spots -->
            <div style="position:absolute; left:1465px;  top:219px; outline: none;" v-b-popover.click.blur.top="'Kit WC Spots'" tabindex="0" >  <i v-on:click="clickLight('kitwcspot')" id="kitwcspot" class="fa fa-circle" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1489px;  top:219px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitwcspot').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitwcspot').brightness_hide">  </div>
            <div style="position:absolute; left:1462px;  top:241px;"    class="zone_time_left" > {{zone_kitchen_wc_time == "NaNs"? "" : zone_kitchen_wc_time}} </div>
            <!-- ****************** RGBW LEDS *********************** Kitchen WC Edge RGBW -->
            <div style="position:absolute; left:1460px;  top:170px; font-size:150%; outline: none;" v-b-popover.click.blur.top="'Kit WC Edge RGBW'" tabindex="0" >  <i v-on:click="clickLight('kitwcedgergbw')" id="kitwcedgergbw" class="far fa-square" aria-hidden="false"></i></div>
            <div style="position:absolute; left:1492px;  top:173px;"    class="light_brightness" > <animated-number :value="light_lookup_localname('kitwcedgergbw').brightness_value" :formatValue="formatToValue" :duration="duration" v-if="light_lookup_localname('kitwcedgergbw').brightness_hide"> </div>
            

            <!-- Hidden button behind light icons - old code no longer used -->
            <!-- <div style="position:absolute; left:1457px;  top:217px" >  <button class="btn btn-primary-outline" v-on:click="clickLight('kitwcspot')" v-b-popover.focus.top="'Kit WC Spots'"></button></div> -->



            <!-- ********************************************* SONOS PLAYERS ******************************************* -->
            <!-- ********************************************* SONOS PLAYERS ******************************************* -->
            <div v-if="sonos_table[3].role_boolean" >
              <div style="position:absolute; left:1220px; top:420px; outline:none;  color:#2100a6;" v-b-popover.click.blur.top="'Kit TV Cabinet'" tabindex="0" >  <i id="sonos_kit_tv_cabinet" class="fa fa-headphones"></i></div>
              <div style="position:absolute; left:1240px; top:417px; color:#2100a6; font-size:90%;" class="sonos_volume" > {{sonos_table[3].volume}} </div>
            </div>

            <div v-if="sonos_table[4].role_boolean" >
              <div style="position:absolute; left:785px;  top:50px;  outline:none;  color:#2100a6;"v-b-popover.click.blur.top="'Kit Garden Wall'" tabindex="0" > <i id="sonos_kit_wall" class="fa fa-headphones"></i></div>
              <div style="position:absolute; left:805px;  top:47px;  color:#2100a6; font-size:90%;" class="sonos_volume" > {{sonos_table[4].volume}} </div>
            </div>


        </div>
    </template>

    
    <!-- ****************** USER SELECTION - AUTOMATED LIGHTING STATUS ****************** -->
    <!-- ****************** USER SELECTION - AUTOMATED LIGHTING STATUS ****************** -->
    <template id = "automated lighting status" >
        <div class="input-card" style="position:absolute; width:260px; height:350px; left:20px;  top:560px; "> 
            <div class="card-body" style="position:absolute; width:260px; left:15px;  top:-5px; font-size: 110%; color: white;">Auto Lighting Zone Status</div>
              <div style="font-size: 100%; color: #c2c2c2;">
                <div style="position:absolute; width:120px; left:18px;  top:60px;" >   <button id="Zone_G_Kitchen"   :style="{backgroundColor: zone_lookup_hc2name('Zone_G_Kitchen').zonestatus == 'Active'?'#007a13':'#b80202'}" v-on:click="clickZoneStatus('Zone_G_Kitchen')">  {{zone_lookup_hc2name('Zone_G_Kitchen').zonestatus}}     </button>    </div>
                <div style="position:absolute; width:120px; left:133px; top:60px;" >   Kitchen </div>
                <div style="position:absolute; width:120px; left:18px;  top:100px;" >  <button id="Zone_G_KitCorr"   :style="{backgroundColor: zone_lookup_hc2name('Zone_G_KitCorr').zonestatus == 'Active'?'#007a13':'#b80202'}" v-on:click="clickZoneStatus('Zone_G_KitCorr')">  {{zone_lookup_hc2name('Zone_G_KitCorr').zonestatus}}     </button>    </div>
                <div style="position:absolute; width:120px; left:133px; top:100px;" >  Kitchen Landing </div>
                <div style="position:absolute; width:120px; left:18px;  top:140px;" >  <button id="Zone_G_KitWC"     :style="{backgroundColor: zone_lookup_hc2name('Zone_G_KitWC').zonestatus == 'Active'?'#007a13':'#b80202'}" v-on:click="clickZoneStatus('Zone_G_KitWC')">      {{zone_lookup_hc2name('Zone_G_KitWC').zonestatus}}       </button>    </div>      
                <div style="position:absolute; width:120px; left:133px; top:140px;" >  Kitchen WC </div>
                <div style="position:absolute; width:120px; left:18px;  top:180px;" >  <button>                                                                                                                                                                                    {{zone_lookup_hc2name('Zone_G_Garden').zonestatus}}      </button>    </div>
                <div style="position:absolute; width:120px; left:133px; top:180px;" >  Garden</div>
                <div style="position:absolute; width:120px; left:18px;  top:220px;" >  <button id="Zone_G_GarRoom"   :style="{backgroundColor: zone_lookup_hc2name('Zone_G_GarRoom').zonestatus == 'Active'?'#007011':'#b80202'}" v-on:click="clickZoneStatus('Zone_G_GarRoom')">  {{zone_lookup_hc2name('Zone_G_GarRoom').zonestatus}}     </button>    </div>
                <div style="position:absolute; width:120px; left:133px; top:220px;" >  Garden Room </div>
                <div style="position:absolute; width:120px; left:18px;  top:260px;" >  <button id="Zone_G_GarBath"   :style="{backgroundColor: zone_lookup_hc2name('Zone_G_GarBath').zonestatus == 'Active'?'#007011':'#b80202'}" v-on:click="clickZoneStatus('Zone_G_GarBath')">  {{zone_lookup_hc2name('Zone_G_GarBath').zonestatus}}     </button>    </div>
                <div style="position:absolute; width:120px; left:133px; top:260px;" >  Garden Bath </div>
              </div>
            
        </div> 
    </template>



    <!-- ****************** USER SELECTION - LIGHTING GROUPS ****************** -->
    <!-- ****************** USER SELECTION - LIGHTING GROUPS ****************** -->
    <template id = "lighting group and preset light level shortcuts" >
        <div class="input-card" style="position:absolute; width:310px; height:450px; left:310px;  top:560px; "> 
            <div class="card-body" 
                style="position:absolute; width:260px; left:90px;  top:-5px; font-size: 110%; color: white;">Lighting Groups
                <div style="position:absolute; width:150px; left:-70px; top:58px;" >   <button v-on:click="clickLightGroup('Group Kit All')">          Kitchen All    </button>     </div>
                <div style="position:absolute; width:150px; left:-70px; top:98px;" >   <button v-on:click="clickLightGroup('Group Kit Spot All')">     Kit Spot All   </button>     </div>
                <div style="position:absolute; width:150px; left:-70px; top:138px;" >  <button v-on:click="clickLightGroup('Group Kit All RGBW')">     Kit All RGBW    </button>     </div>
                <div style="position:absolute; width:150px; left:-70px; top:178px;" >  <button v-on:click="clickLightGroup('-')">     -     </button>     </div>

                <div style="position:absolute; width:150px; left:75px; top:58px;" >    <button v-on:click="clickLightGroup('Group Garden All')">       Garden All     </button>     </div>
                <div style="position:absolute; width:150px; left:75px; top:98px;" >    <button v-on:click="clickLightGroup('Group Garden Room All')">  GardRm All     </button>     </div>
                <div style="position:absolute; width:150px; left:75px; top:138px;" >   <button v-on:click="clickLightGroup('Group Ground High RGBW')"> All High RGB   </button>     </div>
                <div style="position:absolute; width:150px; left:75px; top:178px;" >   <button v-on:click="clickLightGroup('Group Ground Low RGBW')">  All Low RGB    </button>     </div>
                <!-- ****************** USER INPUT - LIGHTING SCENES ****************** -->
            </div> 

            <div class="card-body" 
                style="position:absolute; width:260px; left:75px;  top:220px; font-size: 110%; color: white;">Lighting Scenes
                <div style="position:absolute; width:150px; left:-55px; top:58px;">   <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('TV Low')">       TV Low         </button>     </div>
                <div style="position:absolute; width:150px; left:-55px; top:98px;">   <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('TV Medium')">    TV Medium      </button>     </div>
                <div style="position:absolute; width:150px; left:-55px; top:138px;">  <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('')">             -              </button>     </div>
                <div style="position:absolute; width:150px; left:-55px; top:178px;">  <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('')">             -              </button>     </div>

                <!-- relaxing and party are setup in node-red -->

                <div style="position:absolute; width:150px; left:90px; top:58px;">    <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('Dining')">       Dining         </button>     </div>
                <div style="position:absolute; width:150px; left:90px; top:98px;">    <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('Dinner')">       Dinner         </button>     </div>
                <div style="position:absolute; width:150px; left:90px; top:138px;">   <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('Cooking')">      Cooking        </button>     </div>
                <div style="position:absolute; width:150px; left:90px; top:178px;">   <button :style="{color: lighting_disable_scenes? 'grey' : ''}"  :disabled="lighting_disable_scenes" v-on:click="clickLightScene('-')">            -              </button>     </div>
            </div> 
        </div> 
    </template>



        
    <!-- ****************** USER INTERFACE - LIGHTING CONTROL ****************** -->
    <!-- ****************** USER INTERFACE - LIGHTING CONTROL ****************** -->
    <template id = "lighting control" >
        <div class="input-card"    style="position:absolute; width:310px; height:490px; left:650px;  top:560px;"> 
            <div class="card-body" style="position:absolute; width:260px; left:75px; top:-5px; font-size: 110%; color: white;"> Lighting Control </div>

            <div          style="position:absolute; width:250px; left:25px; top:50px; "><label>Light:</label></div>
            <div          style="position:absolute; width:250px; left:25px; top:83px;"><label>Brightness:</label></div>
            <div          style="position:absolute; width:250px; left:73px; top:50px; font-size: 100%; color: white;"><label id="circuit_name">{{ curr_input_circuit }}</label></div>
            <div          style="position:absolute; width:250px; left:143px; top:83px; font-size: 100%; color: white;"><label>{{ input_brightness }}</label></div>
            <b-form-input style="position:absolute; width:250px; left:24px; top:120px;" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" lazy v-on:change="sliderChangeBrightness(input_brightness)" id="range-10" v-model="input_brightness" type="range" min="0" max="100"></b-form-input>       <!-- slider brightness input-->
            <!-- ****************** USER INTERFACE - SLIDER ****************** -->

            <!-- ****************** USER INTERFACE - BRIGHTNESS BUTTONS ****************** -->
            <div style="font-size:90% !important;">
              <div style="position:absolute; width:60px; left:5px;  top:160px;" >    <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('0')">Off</button></div>
              <div style="position:absolute; width:60px; left:50px;  top:160px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('5')">5</button></div>
              <div style="position:absolute; width:60px; left:80px; top:160px;" >    <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('10')">10</button></div>
              <div style="position:absolute; width:60px; left:120px; top:160px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('15')">15</button></div>
              <div style="position:absolute; width:60px; left:160px; top:160px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('20')">20</button></div>
              <div style="position:absolute; width:60px; left:200px; top:160px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('25')">25</button></div>
              <div style="position:absolute; width:60px; left:240px; top:160px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('30')">30</button></div>

              <div style="position:absolute; width:60px; left:5px;  top:197px;" >    <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('40')">40</button></div>
              <div style="position:absolute; width:60px; left:45px;  top:197px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('50')">50</button></div>
              <div style="position:absolute; width:60px; left:80px; top:197px;" >    <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('60')">60</button></div>
              <div style="position:absolute; width:60px; left:120px; top:197px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('70')">70</button></div>
              <div style="position:absolute; width:60px; left:160px; top:197px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('80')">80</button></div>
              <div style="position:absolute; width:60px; left:200px; top:197px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('90')">90</button></div>
              <div style="position:absolute; width:60px; left:240px; top:197px;" >   <button class="button_brightness" :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons" v-on:click="sliderChangeBrightness('99')">99</button></div>
            </div>

            <transition name="fade">  
              <div v-if="colour_picker_hide" id="hide" style="position:absolute; width:150px; left:19px; top:250px;"> 
                <color-picker :width="200" :height="200" :disabled="false" startColor="#ff0000" v-model="color" ></color-picker> 
                <div style="position:absolute; width:50px; left:218px; top:-8px;">Submit</div>
                <div style="position:absolute; width:150px; left:227px; top:20px;"><div class="selected-color-info" aria-hidden="false" focusable="true" v-on:click="colourChange_colourWheel"> <svg height="32" width="32"> <circle cx="16" cy="16" r="15" :fill="color" /> </svg> </div></div> 
                <div v-if="colour_picker_hide" id="hide" style="position:absolute; width:85px; left:205px; top:175px;"><button :style="{color: lighting_disable_slider_buttons? 'grey' : ''}"  :disabled="lighting_disable_slider_buttons"  v-on:click="colourChange('warm')">Warm White</button></div>
              </div>  
            </transition>

        </div> 
    </template>








   <!-- ****************** USER INTERFACE - AUDIO CONTROL ****************** -->
   <!-- ****************** USER INTERFACE - AUDIO CONTROL ****************** -->
   <template id = "audio control">
        <div class="input-card"    style="position:absolute; width:905px; height:490px; left:990px;  top:560px;"> 

            <!-- ****************** CARD HEADER ****************** -->
            <div class="card-body" style="position:absolute; width:260px; left:360px; top:-5px; font-size: 110%; color: white;"> Audio Control </div>

            <!-- ****************** ENABLE/DISABLE SONOS PLAYER ****************** -->
            <div style="position:absolute; width:120px;  left:12px; top:10px; font-size:90%;" >   <button id="sonos_visible"  style="font-size:100% !important;" v-on:click="sonos_visible_update('sonos_visible',true)"> {{sonos_table[0].sonos_visible_label}} </button></div>
            <div style="position:absolute; width:120px;  left:14px; top:42px; font-size:70% !important; color:#6b6b6b;" > {{sonos_visible_timer < 1? "" : sonos_visible_timer }} </div>

            <!-- hide card if disabled -->
            <div v-if="sonos_table[0].sonos_visible">

              <!-- ****************** WARNING - NO PLAYERS ADDED ****************** -->
              <div style="position:absolute; width:200px;  left:115px;  top:-23px; font-size:90%; color:grey;"> {{(sonos_table[0].coordinator != "standalone" || sonos_coordinator_single_player != "")? "" : "** ADD PLAYERS TO GROUP **"}} </div>  

              <!-- ****************** GROUP PLAY/PAUSE-NEXT/PREVIOUS ****************** -->
              <div style="position:absolute; width:180px; left:40px; top:70px;">                  <i v-on:click="shufflePlaylist('shuffle_playlist',true)"   :style="{color: sonos_table[0].shuffle? '#c2c2c2' : 'grey'}"   class="fa fa-random"  aria-hidden="false"  id="shuffle_playlist"> </i></div>
              <div style="position:absolute; width:80px; left:125px; top:65px; font-size: 1.5em"> <i v-on:click="trackChange('previous')"                    class="fa fa-step-backward" aria-hidden="false"  ></i></div>
              <div style="position:absolute; width:80px; left:200px; top:65px; font-size: 1.5em"     v-on:click="playStatusChange()"> 
                                                                                                  <i  v-if="sonos_table[0].playbackstate ==='playing'"       class="fa fa-pause"         aria-hidden="false"> </i>
                                                                                                  <i v-else                                                  class="fa fa-play"          aria-hidden="false">   </i></div>
              <div style="position:absolute; width:80px; left:270px; top:65px; font-size: 1.5em" ><i v-on:click="trackChange('next')"                        class="fa fa-step-forward"  aria-hidden="false"  ></i></div>
              
              <div style="position:absolute; width:80px; left:183px; top:22px; font-size: 1em" > {{ (sonos_table[0].coordinator != "standalone" || sonos_coordinator_single_player != "")? (sonos_table[0].trackposition + ' / ' + sonos_table[0].trackduration) : "" }} </div>



              <!-- ****************** GROUP VOLUME ****************** -->
              <div          style="position:absolute; width:240px; left:27px;  top:114px; font-size:95%;">Group</div>  
              <b-form-input style="position:absolute; width:200px; left:105px; top:114px;"  lazy v-on:change="sliderVolumeChange(sonos_table[0].volume,sonos_table[0].coordinator_name,'Group')" :disabled="this.sonos_table[0].coordinator_name==''? true:false" id="volume_slider" v-model="sonos_table[0].volume" type="range" min="0" max="60"></b-form-input>
              <div          style="position:absolute; width:10px;  left:315px; top:114px; text-align: right;">{{sonos_table[0].volume}}</div>
              <div          style="position:absolute; width:80px;  left:340px; top:118px;"  v-on:click="muteChange(sonos_table[0].mute,sonos_table[0].coordinator_name,'Group')">                <p v-if="sonos_table[0].mute" class="fa fa-volume-mute" aria-hidden="false"></p> <p v-else class="fa fa-volume-up" aria-hidden="false"  ></p></div>

              <div style="position:absolute; width:60px; left:88px;  top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('0',sonos_table[0].coordinator_name,'Group')">    0</p></div>  
              <div style="position:absolute; width:60px; left:112px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('5',sonos_table[0].coordinator_name,'Group')" >   5</p></div>  
              <div style="position:absolute; width:60px; left:134px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('10',sonos_table[0].coordinator_name,'Group')" > 10</p></div>  
              <div style="position:absolute; width:60px; left:166px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('20',sonos_table[0].coordinator_name,'Group')" > 20</p></div>  
              <div style="position:absolute; width:60px; left:198px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('30',sonos_table[0].coordinator_name,'Group')" > 30</p></div>  
              <div style="position:absolute; width:60px; left:230px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('40',sonos_table[0].coordinator_name,'Group')" > 40</p></div>  
              <div style="position:absolute; width:60px; left:262px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('50',sonos_table[0].coordinator_name,'Group')" > 50</p></div>  
              <div style="position:absolute; width:60px; left:294px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('60',sonos_table[0].coordinator_name,'Group')" > 60</p></div>  
              <div style="position:absolute; width:60px; left:326px; top:152px; font-size:90%"> <p v-on:click="sliderVolumeChange('70',sonos_table[0].coordinator_name,'Group')" > 70</p></div>  
                          


              <!-- ****************** INDIVIDUAL DEVICES ****************** -->
              <!-- ****************** INDIVIDUAL DEVICES ****************** -->
              <div          style="position:absolute; width:90px;  left:20px;   top:210px;"><button v-on:click="roleChange(sonos_table[1].role_boolean,'Office AV1')" :style="{color: sonos_table[1].role_boolean? '#c2c2c2':'grey'} ">AV1</button> </div>
              <b-form-input style="position:absolute; width:200px; left:105px;  top:210px;" lazy v-on:change="sliderVolumeChange(sonos_table[1].volume,'Office AV1')" :disabled="!sonos_table[1].role_boolean"  id="volume_slider" v-model="sonos_table[1].volume" type="range" min="0" max="70"></b-form-input>
              <div          style="position:absolute; width:10px;  left:315px;  top:210px; text-align: right;">{{sonos_table[1].volume}}</div>
              <div          style="position:absolute; width:80px;  left:340px;  top:214px;" v-on:click="muteChange(sonos_table[1].mute,'Office AV1')">           <p v-if="sonos_table[1].mute" class="fa fa-volume-mute" aria-hidden="false"></p> <p v-else class="fa fa-volume-up" aria-hidden="false"  ></p></div>

              <div          style="position:absolute; width:90px;  left:20px;  top:270px;"> <button v-on:click="roleChange(sonos_table[2].role_boolean,'Office AV2')" :style="{color: sonos_table[2].role_boolean? '#c2c2c2':'grey'} ">AV2</button> </div>
              <b-form-input style="position:absolute; width:200px; left:105px; top:270px;" lazy v-on:change="sliderVolumeChange(sonos_table[2].volume,'Office AV2')" :disabled="!sonos_table[2].role_boolean"   id="volume_slider" v-model="sonos_table[2].volume" type="range" min="0" max="70"></b-form-input>
              <div          style="position:absolute; width:10px;  left:315px; top:270px; text-align: right;">{{sonos_table[2].volume}}</div>
              <div          style="position:absolute; width:80px;  left:340px; top:274px;" v-on:click="muteChange(sonos_table[2].mute,'Office AV2')">           <P v-if="sonos_table[2].mute" class="fa fa-volume-mute" aria-hidden="false"></P> <P v-else class="fa fa-volume-up" aria-hidden="false"  ></P></div>

              <div          style="position:absolute; width:90px;  left:20px;  top:330px;"> <button v-on:click="roleChange(sonos_table[3].role_boolean,'Kit Cabinet')" :style="{color: sonos_table[3].role_boolean? '#c2c2c2':'grey'} ">K.Cabnt</button> </div>
              <b-form-input style="position:absolute; width:200px; left:105px; top:330px;" lazy v-on:change="sliderVolumeChange(sonos_table[3].volume,'Kit Cabinet')" :disabled="!sonos_table[3].role_boolean"  id="volume_slider" v-model="sonos_table[3].volume" type="range" min="0" max="70"></b-form-input>
              <div          style="position:absolute; width:10px;  left:315px; top:330px; text-align: right;">{{sonos_table[3].volume}}</div>
              <div          style="position:absolute; width:80px;  left:340px; top:334px;" v-on:click="muteChange(sonos_table[3].mute,'Kit Cabinet')">           <P v-if="sonos_table[3].mute" class="fa fa-volume-mute" aria-hidden="false"></P> <P v-else class="fa fa-volume-up" aria-hidden="false"  ></P></div>

              <div          style="position:absolute; width:90px;  left:20px;  top:390px;"> <button v-on:click="roleChange(sonos_table[4].role_boolean,'Kit Garden')" :style="{color: sonos_table[4].role_boolean? '#c2c2c2':'grey'} ">K.Gard</button> </div>
              <b-form-input style="position:absolute; width:200px; left:105px; top:390px;" lazy v-on:change="sliderVolumeChange(sonos_table[4].volume,'Kit Garden')" :disabled="!sonos_table[4].role_boolean"   id="volume_slider" v-model="sonos_table[4].volume" type="range" min="0" max="70"></b-form-input>
              <div          style="position:absolute; width:10px;  left:315px; top:390px; text-align: right;">{{sonos_table[4].volume}}</div>
              <div          style="position:absolute; width:80px;  left:340px; top:394px;" v-on:click="muteChange(sonos_table[4].mute,'Kit Garden')">           <P v-if="sonos_table[4].mute" class="fa fa-volume-mute" aria-hidden="false"></P> <P v-else class="fa fa-volume-up" aria-hidden="false"  ></P></div>


              <!-- ****************** TRACK QUEUE ****************** -->
              <!-- ****************** TRACK QUEUE ****************** -->
              <div          style="position:absolute; width:330px;  left:403px; top:50px;  color:grey; font-size:80%; font-style:italic;">Track</div>  
              <div          style="position:absolute; width:295px;  left:405px; top:68px;  font-size:85%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> {{sonos_table[0].queuePosition}}. {{sonos_queue[0].title}} </div>  
              
              <div          style="position:absolute; width:330px;  left:403px; top:93px; color:grey; font-size:80%; font-style:italic;">Artist</div>  
              <div          style="position:absolute; width:295px;  left:405px; top:111px; font-size:85%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> {{sonos_queue[0].artist}}</div>  

              <div          style="position:absolute; width:330px;  left:403px; top:136px; color:grey; font-size:80%; font-style:italic;">Album</div>  
              <div          style="position:absolute; width:295px;  left:405px; top:154px; font-size:85%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> {{sonos_queue[0].album}}</div>  

              <div          style="position:absolute; width:200px;  left:403px; top:185px; color:grey; font-size:80%; font-style:italic;"> {{(sonos_table[0].coordinator != "standalone" || sonos_coordinator_single_player != "")?  'Queue - ' + sonos_table[0].numberoftracks + ' tracks' : ""}} </div>  
              <div          style="position:absolute; width:300px;  left:405px; top:205px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[1]"> {{sonos_table[0].queuePosition+1}}. {{sonos_queue[1].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:227px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[2]"> {{sonos_table[0].queuePosition+2}}. {{sonos_queue[2].title}} </p> <p v-else>-</p> </div>  
              <div          style="position:absolute; width:300px;  left:405px; top:249px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[3]"> {{sonos_table[0].queuePosition+3}}. {{sonos_queue[3].title}} </p> <p v-else>-</p> </div>    
              <div          style="position:absolute; width:300px;  left:405px; top:271px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[4]"> {{sonos_table[0].queuePosition+4}}. {{sonos_queue[4].title}} </p> <p v-else>-</p> </div>  
              <div          style="position:absolute; width:300px;  left:405px; top:293px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[5]"> {{sonos_table[0].queuePosition+5}}. {{sonos_queue[5].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:315px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[6]"> {{sonos_table[0].queuePosition+6}}. {{sonos_queue[6].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:337px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[7]"> {{sonos_table[0].queuePosition+7}}. {{sonos_queue[7].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:359px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[8]"> {{sonos_table[0].queuePosition+8}}. {{sonos_queue[8].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:381px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[9]"> {{sonos_table[0].queuePosition+9}}. {{sonos_queue[9].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:403px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[10]"> {{sonos_table[0].queuePosition+10}}. {{sonos_queue[10].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:425px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[11]"> {{sonos_table[0].queuePosition+11}}. {{sonos_queue[11].title}} </p> <p v-else>-</p> </div>   
              <div          style="position:absolute; width:300px;  left:405px; top:447px; font-size:80%; white-space:nowrap; overflow:hidden; text-overflow:ellipsis;" class="track_name"> <p v-if="sonos_queue[12]"> {{sonos_table[0].queuePosition+12}}. {{sonos_queue[12].title}} </p> <p v-else>-</p> </div>   


              <!-- ****************** PLAYLISTS ****************** -->
              <!-- ****************** PLAYLISTS ****************** -->
              <div style="position:absolute; width:125px;  left:727px; top:215px;  color:grey; borderColor:grey; font-size:80%; font-style:italic;">Playlists</div>  
              <select class="browser-default custom-select"  @change="onChangePlaylist($event)" style="position:absolute; width:140px;  left:725px; top:240px; font-size:80%; background-color:#1f1f1f; color:#c2c2c2; borderColor:#383838;">
                <option selected style="font-size:130%"> Classical </option>
                <option value="Classical - Relaxing">Relaxing</option>
                <option value="Classical - Upbeat">Upbeat</option>
                <option value="Sleepy Piano">Sleepy Piano</option>
              </select>
              <select class="browser-default custom-select"  @change="onChangePlaylist($event)" style="position:absolute; width:140px;  left:725px; top:280px; font-size:80%; background-color:#1f1f1f; color:#c2c2c2; borderColor:#383838;">
                <option selected style="font-size:125%"> Chill </option>
                <option value="Chill - Adell">Adell</option>
                <option value="Chill - Autumn">Autumn</option>
                <option value="Chill - Super Oldies">Super Oldies</option>
                <option value="Chill - Weekend Rock">Weekend Rock</option>
                <option value="Chill - Post Dinner">Post Dinner</option>
                <option value="Chill - Electro House">Electro House</option>
                <option value="Chill - Old School">Old School</option>
                <option value="Chill - Old School Super">Super Old School</option>
                <option value="Chill - Buddha">Buddha</option>
              </select>

              <!-- ****************** ALBUM ART ****************** -->
              <div v-if="this.sonos_albumart"> <figure class="image__wrapper"> <img class="image__item" :src="sonos_queue[0].albumArtURI" alt="random image" style="position:absolute; left:707px; top:15px; max-width: 20%;"> </figure> </div>
           
            </div>
            </div> 
        </div> 
    </template>
  </div>


    </b-container>

</template>


























<script> 

import AnimatedNumber from "animated-number-vue";
import ColorPicker from "vue-color-picker-wheel";

export default {
  name: "Floorplan",
  
    components: {
      ColorPicker,
      AnimatedNumber,
    },
   

    data() {
      return {

        colour_picker_hide: false,                    //hide/show all elements within the colour picker card
        brightness_value_hide: true,                  //hides brightness value if = 0; required due to animated-numbers (could use a different method to animate)

        curr_input_circuit:"",                        // this is the current user selected circuit
        prev_input_circuit:"Kitchen/Cabinet Lights",  // this is the current user selected circuit
        prev_input_circuit_type:"single",             //single or group of lights

        input_brightness:"",                          // this is the current circuit selected brightness
        color:'#000000',                              // this is the current circuit selected colour (if applicable)
    
        
        current_circuit:"kitcabinet",                 //used to remove fa-beat from last selected curcuit or group of circuits
        lighting_groups_table: [],                    //used to store the lighting group definitions passed from the lighting groups table 
        lighting_groups_run:true,                     //make sure the lighting group var is only updated once
        lighting_groups_records:0,                    //make sure that removefabeat is only run once from clickLight when a group of circuit is selected 

        lighting_disable_scenes: false,               //disable inputs for set time to allow home automation to process the requestg
        lighting_disable_slider_buttons: false,       //disable inputs for set time to allow home automation to process the requestg
        lighting_disable_timer_single: 1500,
        lighting_disable_timer_group: 3500,
        colourChange_colourWheel_current_time: 0,     //stores the os.time to allow a freeze on colour changes 
        duration: 1000,                               //animated-number animation duration in miliseconds


        light_table: [
            // kitchen spots
            {hc2name:"Kitchen/Cabinet Lights",          circuitname:"Cabinet Lights",       localname:"kitcabinet",     brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true},
            {hc2name:"Kitchen/Lounge Lights",           circuitname:"Lounge Lights",        localname:"kitlounge",      brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true},
            {hc2name:"Kitchen/Wall Lights",             circuitname:"Wall Lights",          localname:"kitwall",        brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true},
            {hc2name:"Kitchen/Pendant Light",           circuitname:"Pendant Light",        localname:"kitpendant",     brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true},
            {hc2name:"Kitchen/Island Lights",           circuitname:"Island Lights",        localname:"kitisland",      brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true},
            {hc2name:"Kitchen/Courtyard Uplights",      circuitname:"Courtyard UpLights",   localname:"kitcourtyard",   brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true},
            //kitchen rgbw
            {hc2name:"Kitchen/Skylight Lights",         circuitname:"Skylight Lights",      localname:"kitskyrgbw",     brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            {hc2name:"Kitchen/Ceiling Lights",          circuitname:"Ceiling Lights",       localname:"kitedgergbw",    brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            {hc2name:"Kitchen/Kit Sink RGBW 5PL",       circuitname:"Kit Sink RGBW 5PL",    localname:"kitsinkrgbw",    brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            {hc2name:"Kitchen/Island Low Lights",       circuitname:"Island Low Lights",    localname:"kitislandrgbw",  brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            {hc2name:"Kitchen/Sink and Low Lights",     circuitname:"Sink and Low Lights",  localname:"kitcabinetrgbw", brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            {hc2name:"Kitchen/Drinks Cabinet",          circuitname:"Drinks Cabinet",       localname:"kitdrinksrgbw",  brightness_value:"0",   zonename:"Zone_G_Kitchen",  rgbw:false,     brightness_hide:true,      colour_value:"0"},
            //garden
            {hc2name:"Garden/Bench Wall Lights",        circuitname:"Bench Wall Lights",    localname:"gardenwallbench",brightness_value:"0",   zonename:"Zone_G_Garden",   rgbw:false,     brightness_hide:true},
            {hc2name:"Garden/BBQ Wall Lights",          circuitname:"BBQ Wall Lights",      localname:"gardenwallbbq",  brightness_value:"0",   zonename:"Zone_G_Garden",   rgbw:false,     brightness_hide:true},
            {hc2name:"Garden/Garden Bench Lights",      circuitname:"Garden Bench Lights",  localname:"gardenbench",    brightness_value:"0",   zonename:"Zone_G_Garden",   rgbw:true,      brightness_hide:true,      colour_value:"0"},
            //garden room
            {hc2name:"Garden Room/Spot Lights",         circuitname:"Spot Lights",          localname:"groomspot",      brightness_value:"0",   zonename:"Zone_G_GarRoom",  rgbw:false,     brightness_hide:true},
            {hc2name:"Garden Room/Perimeter Lights",    circuitname:"Perimeter Lights",     localname:"groomedgergbw",  brightness_value:"0",   zonename:"Zone_G_GarRoom",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            //garden bath
            {hc2name:"Garden Bath/Bath Spot Lights",    circuitname:"Bath Spot Lights",     localname:"gbathspot",      brightness_value:"0",   zonename:"Zone_G_GarBath",  rgbw:false,     brightness_hide:true},
            {hc2name:"Garden Bath/Bath Perimeter Light",circuitname:"Bath Perimeter Light", localname:"gbathedgergbw",  brightness_value:"0",   zonename:"Zone_G_GarBath",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            //kitchen landing
            {hc2name:"Corridors/Kit Corr 2x 2P",        circuitname:"Kit Corr 2x 2P",       localname:"kitcorrspot",    brightness_value:"0",   zonename:"Zone_G_KitCorr",  rgbw:false,     brightness_hide:true},
            {hc2name:"Corridors/Kit RGBW Corr Low",     circuitname:"Kit RGBW Corr Low",    localname:"kitcorrlowrgbw", brightness_value:"0",   zonename:"Zone_G_KitCorr",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            {hc2name:"Corridors/Kit RGB Stairs",        circuitname:"Kit RGB Stairs",       localname:"kitcorrstairs",  brightness_value:"0",   zonename:"Zone_G_KitCorr",  rgbw:true,      brightness_hide:true,      colour_value:"0"},
            //kitchen wc
            {hc2name:"Kitchen WC/Kit WC Lights 1P",     circuitname:"Kit WC Lights 1P",     localname:"kitwcspot",      brightness_value:"0",   zonename:"Zone_G_KitWC",    rgbw:false,     brightness_hide:true},
            {hc2name:"Kitchen WC/Kit WC RGBW Perm 2P",  circuitname:"Kit WC RGBW Perm 2P",  localname:"kitwcedgergbw",  brightness_value:"0",   zonename:"Zone_G_KitWC",    rgbw:true,      brightness_hide:true,      colour_value:"0"},
            ],

      
        // TO DO - REMOVE DUPLICATE VARIABLE NAMES // 
        //each AL zone in the floor plan has to be names as per the HC2 Global Variable name
        zone_table: [
            {hc2name:"Zone_G_Kitchen",            zonestatus:"No Data",       lightingPanelName:"Kitchen",},   
            {hc2name:"Zone_G_KitCorr",            zonestatus:"No Data",       lightingPanelName:"Kit Corr",},   
            {hc2name:"Zone_G_KitWC",              zonestatus:"No Data",       lightingPanelName:"Kitchen WC",},   
            {hc2name:"Zone_G_Garden",             zonestatus:"Manual",        lightingPanelName:"Garden",},   
            {hc2name:"Zone_G_GarRoom",            zonestatus:"No Data",       lightingPanelName:"Gardenroom",},   
            {hc2name:"Zone_G_GarBath",            zonestatus:"No Data",       lightingPanelName:"Garden Bath",},
              ],


        //Time remaining 
        zone_kitchen_landing_time:  "0",
        zone_kitchen_wc_time:       "0",
        zone_garden_room_time:      "0",
        zone_garden_bath_time:      "0",


        //used to store Sonos data passed from Node-RED
        sonos_table: [
                      {device:"Group",         volume:"0",       mute:false,      coordinator:"standalone", coordinator_name:"" , numberoftracks:0,
                       singleplayergroup:"",    playbackstate:"playing",    queuePosition:"1",  trackduration:0,    trackposition:0,
                       sonos_visible:true,     sonos_visible_label:"Disabled",    shuffle:false},
                      {device:"Office AV1",    volume:"0",       mute:false,      role:"standalone",        role_boolean:"true"},
                      {device:"Office AV2",    volume:"0",       mute:false,      role:"standalone",        role_boolean:"true"},
                      {device:"Kit Cabinet",   volume:"0",       mute:false,      role:"standalone",        role_boolean:"true"},
                      {device:"Kit Garden",    volume:"0",       mute:false,      role:"standalone",        role_boolean:"true"},
                      ],                              

        sonos_visible_timer: 0,                     //actual timer/counter
        sonos_visible_interval: "",                 //used by  the internal function
        sonos_visible_interval_time: 90,           //seconds before card details are hidden
        sonos_coordinator_single_player: "",        //temp variable to hold player name if only 1 player in the group 

        sonos_queue: [
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
                      {title:"", artist:"", album:"", albumArtURI:""},
 
                    ],

        sonos_albumart: false,       //v-if to hide if no album art to show

        //Temp and Humidity
        sensors:[
            {hc2name:"Kitchen/Kit Din UF Temp1",                       sensor_value:"1",},
            {hc2name:"Kitchen/Kit Liv UF Temp1",                       sensor_value:"0",},
            {hc2name:"Kitchen WC/Kit WC UF Temp1",                     sensor_value:"0",},
            {hc2name:"Kitchen/KitchenGard Temp",                       sensor_value:"0",},
            {hc2name:"Kitchen WC/Kitchen WC Temp",                     sensor_value:"0",},
            {hc2name:"Garden Room/Garden Room Temp",                   sensor_value:"0",},
            {hc2name:"Garden Bath/Garden Bath Temp",                   sensor_value:"0",},
            {hc2name:"Kitchen WC/Kitchen WC Humidity",                 sensor_value:"0",},
            {hc2name:"Kitchen/KitchenGard Humidit",                    sensor_value:"0",},
            {hc2name:"Garden Bath/Garden Bath Humidity",               sensor_value:"0",},
        ],


        sensors1:[
            {hc2name:"Kitchen/Kit Din UF Temp1",                       sensor_value:"10",},
        ],


      };

    }, // --- End of data --- //


    computed: {

    }, // --- End of computed --- //


    methods: {


    //**************************** SONOS METHODS *********************//
    formatToValue(value) {
      return `${ Number(value).toFixed(0)}`;
    },

    // -- Called if a LIGHT BULB is clicked 
    clickLight: function(localname, group_name, record_count) {

        //Retrieve object for the light bulb
        var light_lookup_localname = this.light_lookup_localname(localname);
        
        if (light_lookup_localname.colour_value !== null) {this.color = light_lookup_localname.colour_value};

        //remove fa-beat from prev_circuit
        if (record_count === undefined)  {this.removefabeat()}
        else if (record_count == 1)      {this.removefabeat()} 
              
        var element                   = document.getElementById(localname);                   //the light bulb element
        var circuit                   = document.getElementById('circuit_name');              //the circuit name (in the lighting control card below the floorplan image)
        element.classList.add("fa-beat");                                                     //add fa-beat light circuit
        circuit.classList.add("fa-beat2");                                                    //add fa-beat light name in lighting control card

        //Change background & text colour of popover if AL zone is Active
        var zone_lookup     = this.zone_table;
        var zone_name       = light_lookup_localname.zonename
        zone_lookup         = zone_lookup.find(zone_lookup => zone_lookup.hc2name == zone_name);
        if (zone_lookup.zonestatus == "Active") 
            {
            var root = document.documentElement;
            root.style.setProperty('--popover-background-colour', "#edd9d8");
            }
        else {
            var root = document.documentElement;
            root.style.setProperty('--popover-background-colour', "#fff");
            }
 
        //Grabbing the brightness and colour of the selected light to display in the lighting control section
        var bright_adjust        = light_lookup_localname.brightness_value;                                               
        if (bright_adjust       == ""){bright_adjust = "0"};
        this.input_brightness    = bright_adjust;
        
        if (light_lookup_localname.rgbw === true) 
            {
            this.input_colour       = light_lookup_localname.colour_value;                                                
            this.colour_picker_hide = true;
            }
        else    
            {this.colour_picker_hide = false;}

        //updating the prev & curr input_circuit 
        if (record_count === undefined) {
                                      this.curr_input_circuit      = light_lookup_localname.hc2name    //update with single circuit name
                                      this.prev_input_circuit      = this.curr_input_circuit;          //update prev with curr input_circut name
                                      this.prev_input_circuit_type = "single"
                                      }
        else if (record_count == 1)   {                                                                //run only once for the group of lights
                                      this.curr_input_circuit      = group_name                        //update with group circuit name
                                      this.prev_input_circuit      = this.curr_input_circuit;          //update prev with curr input_circut name
                                      this.prev_input_circuit_type = "group"
                                      }
    },


    removefabeat: function(){
        
        var prev_input_circuit        = this.prev_input_circuit;        
        var prev_input_circuit_type   = this.prev_input_circuit_type;
        var light_lookup_hc2name      = ""
        var last_element              = "";

        //Remove fa-beat from previous selected circut(s)
        if (prev_input_circuit_type == "single") 
            {
            light_lookup_hc2name = this.light_lookup_hc2name(prev_input_circuit);
            last_element         = document.getElementById(light_lookup_hc2name.localname);                
            last_element.classList.remove("fa-beat");
            }                      
        else                                                                                  //remove pulse from previously selected element for each circuit in the group 
            {                                                                              
              var lighting_groups_table = this.lighting_groups_table;                         //retrieve light groups table (loaded from nod-red global variable)
              lighting_groups_table.forEach(item =>
                  {
                      if (item.zone_name == prev_input_circuit)
                          {
                            var light_table   = this.light_table;
                            light_table       = light_table.find(light_table => light_table.hc2name == item.circuit);
                            last_element      = document.getElementById(light_table.localname);
                            last_element.classList.remove("fa-beat");

                          }
                  })
              }
    },
 

    // -- Called if a LIGHTING GROUP button is clicked -- //
    clickLightGroup: function(group_name) {
      
      if (this.lighting_groups_records > 0) {this.lighting_groups_records = 0}                 //reset counter to allow removefabeat to run

      var lighting_groups_table    = this.lighting_groups_table;
      lighting_groups_table.forEach(item =>                                                     //loops through each light in the group and calls clickLight function to deal with each light circuit individually
            {
                if (item.zone_name == group_name)
                    {
                      var light_table = this.light_table;
                      light_table = light_table.find(light_table => light_table.hc2name == item.circuit);
                      this.lighting_groups_records = this.lighting_groups_records + 1
                      console.log("group click - group name  = ", group_name)
                      console.log("group click - local name  = ", light_table.localname)
                      this.clickLight(light_table.localname, group_name, this.lighting_groups_records);
                    }
            })

        if (group_name != "Kit Spot All") {this.colour_picker_hide = true;} else {this.colour_picker_hide = false;}     //kit spot all is the only group with no rgbw lights in it
    },


    // -- Called if a LIGHTING SCENE button is clicked -- //
    clickLightScene: function(group_name) {
        this.curr_input_circuit= "Group " + group_name;
            {
            uibuilder.send({
            'topic':            group_name,
            'payload':          "Scene",
            'page':             "floorplan",
            })

            //disable the pressed button for set time whilst request is processed
            this.lighting_disable_scenes = true
            setTimeout(() => {
              this.lighting_disable_scenes = false
            }, this.lighting_disable_timer_group)
            }
    },
    

    // -- Called if a ZONE STATUS button is clicked -- //
    clickZoneStatus: function(zone_name) {
        var zone_lookup     = this.zone_table;
        zone_lookup         = zone_lookup.find(zone_lookup => zone_lookup.hc2name == zone_name);

        var el = document.getElementById(zone_name);
        //toggle colour of button 
        if (zone_lookup.zonestatus == "Disabled")   {el.style.backgroundColor = "#007011"} //swap to green
        if (zone_lookup.zonestatus == "Active")     {el.style.backgroundColor = "#990202"} //swap to red
        
        // the status is swtiched in subflow = AL Zone Status Updates 
        if (zone_lookup.zonestatus != "Manual")
            {
            uibuilder.send({
            'topic':            "placeholder to make sure things happen",      //send something to make sure "Node: Lighting groups does not err"
            'payload':          zone_lookup.lightingPanelName,
            'zone_status':      true,
            'page':             "floorplan",
            });
            }
    }, // -- End of  -- //

    //this is for the warm white submit button
    colourChange: function(color) {
    // Send COLOUR to Node Red //
    uibuilder.send({             
        'topic':    this.curr_input_circuit,
        'payload':  color,
        'colour':   color,
        'type':     'colour',
        'page':     "floorplan",
    });

    //TIMER to lock user input
    //if group of lights selected, use longer timer
    var curcuit_prefix    = this.curr_input_circuit
    curcuit_prefix        = curcuit_prefix.substring(0, 5);
    var timer = curcuit_prefix == "Group"? this.lighting_disable_timer_group : this.lighting_disable_timer_single

    //disable the pressed button for set time whilst request is processed
    this.lighting_disable_slider_buttons = true
    setTimeout(() => {
      this.lighting_disable_slider_buttons = false
    }, timer);

    }, // -- End of  -- //


    //this is for only the colour wheool submit button (circle)
    colourChange_colourWheel: function() {
    // Send COLOUR to Node Red //

    //TIMER to lock user input
    //if group of lights selected, use longer timer
    var curcuit_prefix    = this.curr_input_circuit
    curcuit_prefix        = curcuit_prefix.substring(0, 5)
    var timer = curcuit_prefix == "Group"? this.lighting_disable_timer_group : this.lighting_disable_timer_single

    var current_time = new Date()
    if ((current_time - this.colourChange_colourWheel_current_time) > timer)        //if enought time has passed allow updates, else do nothing
      {
      uibuilder.send({             
          'topic':    this.curr_input_circuit,
          'payload':  this.color,
          'colour':   this.color,
          'type':     'colour',
          'page':     "floorplan",
      })
      //disable the pressed button for set time whilst request is processed
      this.lighting_disable_slider_buttons = true
      setTimeout(() => {
        this.lighting_disable_slider_buttons = false
      }, timer);
      //reset time
      this.colourChange_colourWheel_current_time = current_time
      }

}, // -- End of  -- //


    changeElement: function(localname,status,colour) {
        //console.log(localname + status + colour);
         
        var el = document.getElementById(localname)
        let light_colour = (colour === null) ? "orange" : colour
        if (status === true)
            {
            el.style.color =  light_colour
            el.style.fontSize = "1.1em"
            el.style.textShadow = "0px 0px 14px #fff700"
            }
        else
            {
            el.style.color = "#636363"
            el.style.fontSize = "0.9em"
            el.style.textShadow = "0px 0px 14px #948f8f"
            }
      },

    //Update time left
    timeLeft: function(time_remaining, zone_name, time_remaining_var) {
        //console.log("up to here1");
        var zone_lookup     = this.zone_table
        zone_lookup         = zone_lookup.find(zones => zones.hc2name == zone_name)
        if (time_remaining == "0" || zone_lookup.zonestatus == "Disabled" || time_remaining === NaN) {this[time_remaining_var] = ""}   
        else {if (time_remaining !== undefined) {this[time_remaining_var]  = time_remaining + "s"}}
      },


    // Called if slider value has been changed
    sliderChangeBrightness: function(input_brightness)  {
    // Send Updated BRIGHTNESS to Node Red //
    uibuilder.send({
        'topic': this.curr_input_circuit,
        'payload': Number(input_brightness),
        'brightness': Number(input_brightness),
        'page':             "floorplan",
    });

    //if group of lights selected, use longer timer
    var curcuit_prefix    = this.curr_input_circuit
    curcuit_prefix        = curcuit_prefix.substring(0, 5);
    var timer = curcuit_prefix == "Group"? this.lighting_disable_timer_group : this.lighting_disable_timer_single

    //disable the pressed button for set time whilst request is processed
    this.lighting_disable_slider_buttons = true
    setTimeout(() => {
      this.lighting_disable_slider_buttons = false
    }, timer);
    
    }, // -- End of  -- //



    //**************************** SONOS METHODS *********************//

    // Called if slider value has been changed
    sliderVolumeChange: function(volume,player_name,group)  {
    this.sonos_visible_timer = this.sonos_visible_interval_time   //extend timer before card is disabled
    uibuilder.send({
        'device': group,                                          //optional - was volume change sent by the group device?
        'playername': player_name,
        'type': "volume",
        'payload': volume,
        'page': "floorplan_sonos",
    });
    }, // -- End of  -- //


  // Called if mute button has been pressed
    muteChange: function(mute,player_name,group)  {
    this.sonos_visible_timer = this.sonos_visible_interval_time   //extend timer before card is disabled
    
    uibuilder.send({
        'device': group,                                          //optional - was mute change sent by the group device?
        'playername': player_name,
        'type': "mute",
        'payload': mute = !mute,
        'page': "floorplan_sonos",
    });
    }, // -- End of  -- //



  // Called if role button has been pressed4
    roleChange: function(role_boolean,player_name)  {
    this.sonos_visible_timer = this.sonos_visible_interval_time    //extend timer before card is disabled
    var second_player_joining = false

    if (this.sonos_coordinator_single_player != "")                //if singleplayer is populated and rolechange has been called, clear it as either no player is selected or a group of 2 is being formed  
         {
           second_player_joining = this.sonos_coordinator_single_player != player_name? true : false
           this.sonos_coordinator_single_player = ""
            uibuilder.send({
              'type': "singleplayergroup",
              'page': "floorplan_sonos",
              'test': "test",
            });                                                                                    //manage sonos_table to force player name into the group.coordinator property
        }
    else {
          this.sonos_coordinator_single_player = this.sonos_table[0].coordinator == "standalone"?  player_name : ""           //store player name if it is the only player in the group
          this.manageSinglePlayerGroup () 
          this.sonos_coordinator_single_player = this.sonos_table[0].coordinator == "standalone"?  player_name : ""           //store player name if it is the only player in the group
         }

    uibuilder.send({
        'type': "role",
        'playername': player_name,
        'payload': role_boolean = !role_boolean,
        'page': "floorplan_sonos",
        'singleplayergroup' : this.sonos_table[0].singleplayergroup,
        'second_player_joining': second_player_joining,
    });

    }, // -- End of  -- //




  //manages the workaround to allow a single player to "create" a group, despite Sonos supporting this functionality
  manageSinglePlayerGroup: function() {
  this.sonos_coordinator_single_player = this.sonos_table[0].coordinator != "standalone" ? "" : this.sonos_coordinator_single_player    //if there are 2 or more players in the group, reset the single_player varaible

  if (this.sonos_coordinator_single_player != "")                                                                                       // if the single player variable != "" ie if there is only 1x player in the group
    {
    var playername = this.sonos_coordinator_single_player
    this.sonos_table[0].singleplayergroup = playername                                                                                  //set singleplayergroup property
    this.sonos_table[0].coordinator_name = playername                                                                                   //over-ride the inbound data sonos_table coordinator to = single player if there is 1 player in the group

    var sonos_table = this.sonos_table
    sonos_table = sonos_table.find(player => player.device == playername)                                                               //find the object for the individual device
    
    sonos_table.role = "coordinator"                                                                                                    //over-ride the inbound data for the actual device
    sonos_table.role_boolean = true                                                                                                     //over-ride the inbound data for the actual device
    this.sonos_table[0].volume = sonos_table.volume                                                                                     //sync group volume with single player (group) volume 
    }
  else
    {
    this.sonos_coordinator_single_player = this.sonos_table[0].singleplayergroup
    }
  },
  



  // Called if play-pause status buttons have been pressed
    playStatusChange: function()  {
    this.sonos_visible_timer = this.sonos_visible_interval_time   //extend timer before card is disabled
    var playbackstate = this.sonos_table[0].playbackstate;
    playbackstate = playbackstate == "playing"? "group.pause":"group.play"
    uibuilder.send({
        'playername': this.sonos_table[0].coordinator_name,
        'type': "playstatus",
        'topic': playbackstate,
        'page': "floorplan_sonos",
    });
    }, // -- End of  -- //



  // Called if track change  buttons have been pressed
    trackChange: function(action)  {
    this.sonos_visible_timer = this.sonos_visible_interval_time   //extend timer before card is disabled
    var action = action == "next"? "group.next.track":"group.previous.track"

    uibuilder.send({
        'device': this.sonos_table[0].device,
        'playername': this.sonos_table[0].coordinator_name,
        'coordinator': this.sonos_table[0].coordinator,
        'type': "trackchange",
        'topic': action,
        'page': "floorplan_sonos",
    });
    }, // -- End of  -- //


  // Called if playlist has been selected from drop down
    onChangePlaylist: function(event) {
        console.log("yo no yo no", event.target.value)
          this.playlistSet(event.target.value)
    },


  // Change playlist in Sonos
    playlistSet: function(playlist_name)  {
    this.sonos_visible_timer = this.sonos_visible_interval_time   //extend timer before card is disabled
    console.log("up to here playslist selection")
    uibuilder.send({
        'type': "playlist",
        'topic': "group.clear.queue",
        'xyz': this.sonos_table[0].coordinator,
        'payload': playlist_name,
        'playername': this.sonos_table[0].coordinator_name,
        'page': "floorplan_sonos",
    });
    }, // -- End of  -- //


  // Called if shuffle has been toggled
    shufflePlaylist: function(element_name,flip)  {
    this.sonos_visible_timer = this.sonos_visible_interval_time   //extend timer before card is disabled
    var shuffle_status = this.sonos_table[0].shuffle

    if (flip === true)
    {
    shuffle_status = !shuffle_status
    uibuilder.send({
        'coordinator': this.sonos_table[0].coordinator,
        'playername': this.sonos_table[0].coordinator_name,
        'type': "shuffle",
        'payload': shuffle_status,
        'page': "floorplan_sonos",
    });
    }
    // toggle colour of shuffle icon
    var el = document.getElementById(element_name);
    if (shuffle_status === true)   {el.style.color = "#c2c2c2"} //swap to green
    if (shuffle_status === false)  {el.style.color = "grey"} //swap to red

      }, // -- End of  -- //

        

  // Enable / Disable Sonos Player
    sonos_visible_update: function(element_name,flip)  {

      var value = this.sonos_table[0].sonos_visible
      
      if (flip === true)
        {
        value = !value
        this.sonos_table[0].sonos_visible = value
        var label = this.sonos_table[0].sonos_visible_label = value? "Enabled":"Disabled"
        uibuilder.send({
          'type': "FP_Sonos_Data",
          'property': "sonos_visible",
          'label': label,
          'value': value,
          'page': "floorplan_sonos",
        })
        }
    
      //toggle colour of button & transition
      var el = document.getElementById(element_name);
      if (value === true)   
            {
            el.style.backgroundColor = "#007011"         //swap to green
            }
      if (value === false)  
            {
            el.style.backgroundColor = "#2e2e2e"        //swap to dark grey
            }

      //setinterval timer to disable the audio card
      if (value == true) 
            {
            this.sonos_visible_timer = this.sonos_visible_interval_time
            
            this.sonos_visible_interval = setInterval(function(){
              this.sonos_visible_timer = this.sonos_visible_timer -1
              if (this.sonos_visible_timer <1) 
                  {
                    if (this.$route.path == "/Floorplan") 
                      {
                      this.auto_hide_sonos_card()
                      clearInterval(this.sonos_visible_interval)
                      }
                  }
            }.bind(this), 1000);
            }
      else  {
            this.sonos_visible_timer = 0
            clearInterval(this.sonos_visible_interval)
            }
    }, // -- End of  -- //



    auto_hide_sonos_card: function() {
    this.sonos_table[0].sonos_visible = false
    var value = this.sonos_table[0].sonos_visible
    this.sonos_table[0].sonos_visible_label = "Disabled"
    var label = this.sonos_table[0].sonos_visible_label
    uibuilder.send({
      'type': "FP_Sonos_Data",
      'property': "sonos_visible",
      'label': label,
      'value': value,
      'page': "floorplan_sonos",
    })

  var el = document.getElementById('sonos_visible');
  if (value === false)  
      {
      el.style.backgroundColor = "#2e2e2e"        //swap to dark grey
      }
  }, // -- End of  -- //

   


    //**************************** LOOKUPS *********************//

    //Lookup sensor data
    sensor_lookup: function(hc2_name) {
        return this.sensors.find(sensor => sensor.hc2name == hc2_name); // returns whole object found
      },

    //Lookup light data - hc2 name
    light_lookup_hc2name: function(hc2_name) {
        return this.light_table.find(lights => lights.hc2name == hc2_name); // returns whole object found
      },

    //Lookup light data - local name
    light_lookup_localname: function(localname) {
        return this.light_table.find(lights => lights.localname == localname); // returns whole object found
      },

    //Lookup zone data - hc2 name
    zone_lookup_hc2name: function(hc2name) {
        return this.zone_table.find(zones => zones.hc2name == hc2name); // returns whole object found
      },

    //Lookup sonos - player data
    sonos_player_lookup: function(player_name) {
        return this.sonos_table.find(sonos => sonos.device == player_name); // returns whole object found
      },

    //Lookup sonos - player volume
    sonos_player_lookup_volume: function(player_name) {
        var player_object = this.sonos_table.find(sonos => sonos.device == player_name); // returns whole object found
        return player_object.volume; 
      },

    //Refresh entire floorplan page
    reloadPage(){
    window.location.reload()
      },
    
    }, // --- End of methods --- //











    // Start-up
    mounted() {

          
        /** **REQUIRED** Start uibuilder comms with Node-RED */
        // uibuilder.start();
        uibuilder.start('/home', '/uibuilder/vendor/socket.io')

        // run once on mount to refresh colour of button - turn sonos panel on/off
        this.sonos_visible_update('sonos_visible',true);
        //this.shufflePlaylist('shuffle_playlist',false);  

        // msg is updated when a standard msg is received from Node-RED
        uibuilder.onChange('msg', (msg) => {
        if (msg.page == "floorplan" && this.$route.path == "/Floorplan") {                            //only run code if correct message type has been received


            // prepare device specific variables based on the MSG TOPIC of each incoming MSG
            // LIGHTING
            var device_name     = msg.topic;
            var status          = "";       // stores is a light in on/off ie brightness > 0 ? on : off


            var light_lookup_hc2name  = this.light_lookup_hc2name(device_name)

            // SENSORS - TEMP & HUMIDITY
            var sensors_lookup  = this.sensors;
            sensors_lookup      = sensors_lookup.find(sensors_lookup => sensors_lookup.hc2name == device_name);


            // AUTO LIGHTING ZONES
            var zone_name       = msg.topic;
            var zone_lookup     = this.zone_table;
            zone_lookup         = zone_lookup.find(zone_lookup => zone_lookup.hc2name == zone_name);


            //Update variable with time remaining before auto lights are off automatically - using one of the circuits in each zone
            if (msg.topic == "Corridors/Kit Corr 2x 2P")        {this.timeLeft(msg.time_remaining-1, "Zone_G_KitCorr",  "zone_kitchen_landing_time")};
            if (msg.topic == "Kitchen WC/Kit WC Lights 1P")     {this.timeLeft(msg.time_remaining-1, "Zone_G_KitWC",    "zone_kitchen_wc_time")};
            if (msg.topic == "Garden Bath/Bath Spot Lights")    {this.timeLeft(msg.time_remaining-1, "Zone_G_GarBath",  "zone_garden_bath_time")};
            if (msg.topic == "Garden Room/Spot Lights")         {this.timeLeft(msg.time_remaining-1, "Zone_G_GarRoom",  "zone_garden_room_time")};


            // UPDATE BRIGHTNESS AND COLOUR BASED ON MSG'S (LIVE AND CACHED) RECIEVED FROM NODE-RED
            if (light_lookup_hc2name  !== undefined)
            {   
                // 2x vars have to be here to stop errors if msg.topic does not exist in the "Devices" variable defined in the data section
                //COLOUR 
                if (msg.colour !== undefined)
                {

                    light_lookup_hc2name.colour_value = msg.colour;                                                                                       
                    if (light_lookup_hc2name.brightness_value > 0) {status = true} else {status = false}                                                     
                        this.changeElement(light_lookup_hc2name.localname,status,msg.colour)
                }
                 

                //BRIGHTNESS
                if (msg.brightness !== undefined  )
                {
                    //console.log("uop to here before = ", msg.brightness)
                    var duration = this.duration;
                    if (msg.brightness == 0)      {setTimeout(function() {light_lookup_hc2name.brightness_hide = false, duration})} 
                    else                          {light_lookup_hc2name.brightness_hide = true};                                              //using v-binding hides brightness value if = 0
                    //if (msg.brightness == 0) {msg.brightness = ""}                                                                            /// otherwise 0 will be shown on the floor plan when lights are off - it's neater with nothing showing


                    light_lookup_hc2name.brightness_value   = msg.brightness;
                    if      (msg.brightness > 0 && light_lookup_hc2name.rgbw == true)      {this.changeElement(light_lookup_hc2name.localname,true,light_lookup_hc2name.colour_value)} 
                    else if (msg.brightness > 0 && light_lookup_hc2name.rgbw == false)     {this.changeElement(light_lookup_hc2name.localname,true,"orange")} 
                    else                                                                   {this.changeElement(light_lookup_hc2name.localname,false)}
                }
            }


            // UPDATE SENSOR DATA
            if (sensors_lookup  !== undefined)
            {  
                sensors_lookup.sensor_value = msg.payload;
            }

            

            //ZONE STATUS (AUTO LIGHTING)
            //It should always pass as UIBUILDER is getting a handpicked set of Zone statuses
            if (zone_lookup !== undefined)
            {
                //ZONE STATUS
                if(msg.al_zone_status !== undefined)
                {
                    zone_lookup.zonestatus = msg.al_zone_status;
                }
            }




            //LIGHTING CONTROL - USER INPUT // 
            // Updates the lighting control values on incoming message to keep them sync'd if a user makes a change outside of this web page
            if (msg.topic == this.curr_input_circuit) {
                if (msg.brightness !== undefined) {this.input_brightness = msg.brightness}
                if (msg.colour     !== undefined) {this.color     = msg.colour}
            }


            //STORE LIGHTING GROUPS - RUN ONLY ONCE WHEN INJECTED
            if (msg.lighting_groups !== undefined){
              if (this.lighting_groups_run === true) {
                this.lighting_groups_table = msg.lighting_groups;
                var temp = this.lighting_groups_table;
                this.lighting_groups_run = false;
              }
            }


            //STORE SONOS DATA - FRESH DATA INJECTED EVERY SECOND UNLESS REFRESH TURNED OFF
            if (msg.sonos !== undefined){
                this.sonos_table      = msg.sonos;
                if (this.sonos_table[0].sonos_visible_label == "daily disabled") {this.sonos_visible_update('sonos_visible',false)}
                this.manageSinglePlayerGroup ()                                                                                        //manage workaround to allow a single player to form a group
                    {
                    }
                
              }

            if (msg.sonos_queue !== undefined){
                this.sonos_queue      = msg.sonos_queue
                this.sonos_albumart = (this.sonos_queue[0].albumArtURI != null) ? true:false                                             //v-if to hide if no album art to show
              }

         
        }});

    }, // --- End of mounted hook --- //

}// -- End of Export -- //

</script>














<style>

:root{
  
  /* ***************** FLOORPLAN  ***************** */
    --popover-background-colour: #fff;
  /**************** LIGHT POSITIONS X,Y *******************/
  --value_adj:  24px;
  --kitcabinet_left: 1320px;
  --kitcabinet_top:   360px;
  
  /* AUDIO */
  --sonos_visible_interval_timer: this.sonos_visible_interval_time;

}
  

</style>





<style lang="scss" scoped>

/* Cloak elements on initial load to hide the possible display of {{ ... }} 
 * Add to the app tag or to specific tags
 * To display "loading...", change to the following:
 *    [v-cloak] > * { display:none }
 *    [v-cloak]::before { content: "loading…" }
 */


 [v-cloak]::before { content: "loading…" }
 
@import url(https://fonts.googleapis.com/css?family=Barlow);

#color-wheel {
  margin-left: auto;
  margin-right: auto;
}


 


/**************** INTERACTIVE LIGHTS *******************/
/* BUTTONS HIDDEN BEHIND LIGHTS ON FLOOR PLAN */
.btn-primary-outline {
  background-color: transparent !important;
  border-color: transparent !important;
  box-shadow: 0 0 0 0 #1c1c1c !important;
}
.btn:focus {
  outline: none;
  box-shadow: none;
}

.button_brightness {
  background-color: transparent !important;
  border-color: transparent !important;
  box-shadow: 0 0 0 0 #1c1c1c !important;
}

/* LIGHT BRIGHTNESS VALUE NEXT TO LIGHT BULB */
.status[animated-number="0"] {
  font-size: 220% !important; 
  display:none;
}

.light_brightness {
  font-size: 90% !important; 
  color: #383737;
}
.fa-superpowers{
  font-size: 20px !important; 
}
.zone_time_left{
  font-size: 70% !important; 
  color: #545454;
}
.light_name{
  color: #616161;
  font-size: 70%;
}

/**************** INTERACTIVE LIGHTS *******************/



/**************** LIGHTING SCENES *******************/
.fa-television{
  color: #404040;
}
.fa-desktop{
  color: #404040;
}
.fa-cutlery{
  color: #404040;
}
.fa-square{
  transform: scale(1.3,.7);
}
.skylight{
  transform: scale(1.3,.7);
}
.fa-window-minimize{
  transform: scale(1.1,1); 
}

/**************** SENSORS *******************/
.sensors{
  color: #000;
  font-size: 70%;
}
.fa-thermometer-empty{
  color: #000;
}





/**************** LIGHTING CIRCUIT DESCRIPTION POPUP WINDOW *******************/
/* POP-UP BOX FOR LIGHTS ON FLOOR PLAN - f0f0f0*/
.popover {
  border: 2px transparent;
  background-color: var(--popover-background-colour);
  font-size: 12px;
}
.popover .arrow {
  display: none;
}



/**************** CARDS *******************/
/*****************MENU HEADER AT TOP OF THE SCREEN*************/
.header-card {
  color:#ffffff;  
  background-color: var(--body-background-colour);
  font-size: 22px !important;
  height: 53px;
  box-shadow: 0 5px 12px 0 var(--box-shadow);
  align-content: center;
  /*text-shadow: 10px 1px 8px #000"*/  
}

/*****************ALL THE INPUT CARDS BELOW THE FLOOR PLAN*****/
.input-card{
  background-color: var(--card-background-colour);
  box-shadow: 0 5px 12px 0 var(--box-shadow);
  border-radius:.15rem!important;
}



/**************** AUDIO *******************/
.track_name{
  white-space:nowrap; 
  overflow:hidden; 
  text-overflow:ellipsis;
  font-size:90%;
}

.shuffle_active{
  color:grey;
}

.shuffle_inactive{
  color:#fff;
}

/**************** AUDIO *******************/



/**************** ANIMATIONS *******************/
/*ANIMATIONS LIST: https://www.vuetoolbox.com/projects/vue2-animate */
.fa-beat {
  animation:fa-beat 1.7s ease infinite;
}
@keyframes fa-beat {
  0% {transform:scale(1)}
  25% {transform:scale(1.4)}
  50% {transform:scale(1)}
  75% {transform:scale(1.4)}
}

.fa-beat2 {
  animation:fa-beat2 5s;
}
  @keyframes fa-beat2 {
    0% {transform:scale(2)}
    33% {transform:scale(1)}
    66% {transform:scale(2)}
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 2s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}


/* AUDIO PANEL - BUTTON TRANSITION */
.greyout-x-seconds {
  animation:greyout-x-seconds 125s;
}
  @keyframes greyout-x-seconds {
    0%    {background-color:#007011}
    80%    {background-color:#007011}
    100%   {background-color:#545454}
}


</style>