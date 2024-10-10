# ASCII Art Converter
🚧 Heads up! This project is still in development - expect breaking changes along the way. 🚧

![image](https://github.com/user-attachments/assets/9e4183e3-b970-4346-8563-5a87e825779c)

## Overview

This tool converts png/jpeg images into ASCII art while detecting edges and their angles within an image to map them to special characters.

Written in pure Go with no external dependencies.

## Example

<details>
<summary>1. Input image</summary>
<img src="https://github.com/user-attachments/assets/c8af42ce-e296-4625-bf1c-ff6551ee5572" />
</details>

<details>
<summary>2. Preprocess image with Extended Difference of Gaussians </summary>
<img src="https://github.com/user-attachments/assets/a2cdcbe6-f434-467b-bebb-547b74deceda"/>
</details>

<details><summary>3. Detect and map on XDoG Output via Sobel filter</summary>
  
  ```text
                                                                                                |       //             |      
                                                ____________                                   //      //              |      
                        _______         __________ ____    ______________                      \\    ///               |     /
                     ///      ___________                               ___________             \\__//                 |   ///
                 ////                                                              \______                             |  //  
              ////                                                                       ____\\                        |///   
           ///                                                 _________________              \\\\                            
       ////                                           _______/                   \___\_\|         ______                      
    ////                                         ______                                \\\             _\\                    
 __//                                       /____                                        \__              \\                  
                                          ///                                              \_\             \\___              
                                       _//                                                   /\_           \__  \\\           
 _\                                _///_                                                 /____/             \\_   \           
  \\\                          __/_                                                     /\_      \_/               \\         
    |                    _______                                                       /_//                          \\\      
    |                ////                                                           ////                               \|     
   /|              ///                                                          ___/_                                   |     
  //             |//                                                       /____        //|                             |     
 //             //                                                        |           /_  |\                            \\\   
               //                                    /__                  |          /     \\                             \|  
             ///                                ____/___                  |         |       \\                             |  
            //                            ____//____/                     |         _\       \\\\                         ||  
            /                      ________ _ ///                         |\         ||          ____                     /|  
 \\         \\               _____ |    //____          _____              \\\        |____        ___/                   |   
  \\          \\\            \__________/       ______________________       \\           ___________                     |   
   \\           \\\             _        /________                  __________/                                          //   
     \\           \\_____       /________/                                                                             //     
      \\\               ________/                                                                                    //       
        \\\                                                                                                         //        
          \\\                                                                                                     ///         
            \\\\                                                                                               ////           
                \___                                                                                       __///              
                    \\\\                                                                                ////                  
                        \\__                                                                         ////                     
                            _____                                                               ____/                         
                                 __________                                            _________                              
                                          _________                            _________                                      
                                                  ______________________________                                              
                                                                                                                              
                                                                                                                               
```
</details>


<details> <summary>4. Map original image to ASCII characters</summary>

```text
 ..............           .............                                           .......::::::***++%%%+*:::::::::::::***++++%
  ...............            .........        ...:::..::::::.........              .......::::****++%%+*:..:::::::::::***+++++
             ..        .:****::.........:::**+++++++++++++++++++++++++**:......      .......::****++%+*:....::::::::::***++++*
                   .:*++++++++++++++++++++++++++++++++++++++++++++++++**+++++++++**:.   ......:::*++*:.......:::...::::**+++*:
                .:*++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++*****+***::::....:::::...............:::*****:.
             .*++++++++++%%%%+++++++++++++++++++++++++++++++++++++++++++++++++++**+++++*+***++*:....................::****::..
         .:*++++++%%%%%+++++++++++++++++++++++++++++++++++++++++::*******:**+**+++++**++*******+*:::...............:::***::...
      .:*+++%%++++++++++++++++++++++++++++++++++++++++++*****:.  .:..........:...::***::*+**************:...........::::::....
   .:*+++++%%++%+++++++++++++++++++++++++++++++++++*::...:. . .....      .:..:::.:..:::**++++************+:.........::::......
 *++++++++%%++%%%+++++++++++++++++++++++++++++**: .. ...:      ..::     ...........::*:.::***+++**********+*:..  .............
 +++++++++%++++%%%+++++++++++++++++++++++++*:        .  ...... .::.   ..  ..*:......::::.:*::**++++*************:.............
 ++++++++%++%+%%%+++++++++++++++++++++++*:.    .     .:....... .:::...   ... .. ...:::.::.:::*****++*****+*******+*...........
 *++++++%++%%+%+++++++++++++++++++++**:...      ...:.       .... ....:.    ...::.:::::::***+*****+****+++%+*******+*...... ...
  .*+++%+%%%+%+++++++++++++++++++*:.::.:..       ...      ...........::... ....:.:::*:::******+*****++%%%+%+*******+*:.    ...
   .++%++%%+++++++++++++++***::......:::.. :              :............::..:::::::::*::::***+++%+:*+++++%%%%+*********+*: ....
   :+%++%%++%+++++++++*:......::..:.:*....                   .. ...::::*:::::::::::::**+++++++++++%++++++++%%***********+. ...
  .++++%%++%+++++++**.........:.. ...:*.. ...        :**.:.......::****:.::::.::**++++++******+%%%++++++++++%+*******+*++. ...
 .++++%%++++**++***:..:::.....:..   . .:.....        ..:..:::::::::::....:**+++++++*********+%%%%+++++++++++%******+++*++:....
 +++++++++%+**+****:.....:.:..............::.....   ...:***::::::.......::**%%+++++*+*******+%%%%%+++++++++++************++:..
 ++++++++++***+***::.:....::.::...........::::::..::*******:.:::..... ::::*+%%++++++****:****+%%%%%+++++++++***************+..
 +++++++++********:::::::.:....::...::::::.::************:::::..     :::::*+%%+++++****::::::*+%%%%%+++++++******+++++++**++..
 +++++++++*******::::..:::::..::::::::::**************::::.       ...:::::*+%%++++******:...:::**++%%%+++****++++++++****++:..
 *++++++++*******:::::::::.:::::******+**********::::.... ....    .:.....::*+%%+++++++*:::::::::::::*******++++++++******++..:
 *+++++++++*****:::::*:..:*********:*++******::. ..::::*******:...:::::::..::*+++++**********************+++++***********+%:::
  *+++++++++++***::::.::*::************::..:::::****************************:*****+++++***************+++++++************++.::
   :++++++++++++****::.::..:::::::::::::*******+**++*+++++*********************++++++++++++++++++++++++++++++++++******+++...:
     :*++++++++++++******:::::::***********+++++++++++**++++++***********++++++++++++++++++++++++++++++++++++++++***++++:....:
      .*+++++++++++++++++++******+++++++++***++++++++++++++++++++++++++++***++++++++++++++++++++++++**+++++++*******++:.......
        :*+++++++++++++++++++++***++++++++++***++++++++++++++++++++++++++++++++++++++++++++++++++++++++++**********++:........
          .*+++++++++++++++++++++**++++++++++***++++++++++++++++++++++++++++++++++++++++++++++++++++++***********++*..........
             :**++++*++++++++++++***+++++++++++***++++++++++++++++++++++++++++++++++++*++++++++++++**********++++:. ..........
                .:**++++++++++++++***++++++++++++***+++++++++++++++*++++++++++++++++++++****************++++**:.  ............
                     :**++++++++++****++++++++++++****+++++++++++++++****++++++++++++++++*************+++*..        ..........
                        .:**++++++******++++++++++++****+++++++++++++*********+++++++++++*********++++*:       .  ............
                            ..:**++++++++++++++++++*********+++++++++*****************+++++++++++*:..         ................
                                  ..::******+++++++++**********++++++++***********++++++**:::..           ....................
                                            ..:*****++++++++++++++****+++++++++++**::.                 .......................
                                                      .........    ........                            .......................
                                                                                                      ........................
                                                                                                   ...........................
```
</details>

<details><summary>5. Overlay edges on base ASCII mapping</summary>

```text
 ..............           .............                                           .......::::::*|*++%%%+//::::::::::::*|*++++%
  ...............            .........        ..____________.........              .......::::*|/*++%%+//..:::::::::::*|*+++++
             ..        ._______.........__________+____++++______________......      .......::*\\*++%///....::::::::::*|*++++/
                   .:///++++++___________+++++++++++++++++++++++++++++**___________:.   ......::\\__//.......:::...::::|*++///
                .////++++++++++++++++++++++++++++++++++++++++++++++++++++++++++****\______::....:::::...............:::|**//:.
             .////+++++++%%%%+++++++++++++++++++++++++++++++++++++++++++++++++++**+++++*+____\\:....................::*|///:..
         .:///++++%%%%%++++++++++++++++++++++++++++++++++++++++_________________++++**++******\\\\::...............:::***::...
      .////+%%++++++++++++++++++++++++++++++++++++++++_______/.  .:..........:...\___\_\|+********______:...........::::::....
   .////+++%%++%+++++++++++++++++++++++++++++++++______..:. . .....      .:..:::.:..:::\\\+++**********_\\:.........::::......
 __//+++++%%++%%%+++++++++++++++++++++++++++/____ .. ...:      ..::     ...........::*:.:\__*+++**********\\:..  .............
 +++++++++%++++%%%++++++++++++++++++++++++///        .  ...... .::.   ..  ..*:......::::.:*\_\*++++********\\___:.............
 ++++++++%++%+%%%++++++++++++++++++++++_//.    .     .:....... .:::...   ... .. ...:::.::.:::/\_**++*****+*\__**\\\...........
 _\+++++%++%%+%++++++++++++++++++++_///_..      ...:.       .... ....:.    ...::.:::::::*/____/**+****+++%+*\\_***\*...... ...
  \\\++%+%%%+%+++++++++++++++++__/_.::.:..       ...      ...........::... ....:.:::*:::/\_***+**\_/++%%%+%+*******\\:.    ...
   .|+%++%%++++++++++++++_______.....:::.. :              :............::..:::::::::*::/_//*+++%+:*+++++%%%%+********\\\: ....
   :|%++%%++%++++++++////.....::..:.:*....                   .. ...::::*::::::::::::////++++++++++%++++++++%%**********\|. ...
  ./|++%%++%+++++++///........:.. ...:*.. ...        :**.:.......::****:.::::.::___/_+++******+%%%++++++++++%+*******+*+|. ...
 .//++%%++++**++*|//..:::.....:..   . .:.....        ..:..:::::::::::....:*/____+++*****//|*+%%%%+++++++++++%******+++*+|:....
 //+++++++%+**+*//*:.....:.:..............::.....   ...:***::::::.......::|*%%+++++*+*/_**|\+%%%%%+++++++++++***********\\\:..
 ++++++++++***+//*::.:....::.::...........::::::..::*/__***:.:::..... ::::|+%%++++++*/**:**\\+%%%%%+++++++++**************\|..
 +++++++++***///**:::::::.:....::...::::::.::***____/___*:::::..     :::::|+%%+++++*|**:::::\\+%%%%%+++++++******+++++++**+|..
 +++++++++**//***::::..:::::..::::::::::**____//____/*::::.       ...:::::|+%%++++**_\**:...:\\\\++%%%+++****++++++++****+||..
 *++++++++**/****:::::::::.:::::***________*_*///::::.... ....    .:.....:|\+%%++++++||::::::::::____******++++++++******+/|.:
 \\++++++++*\\**:::::*:..:***_____*|*++*//____:. ..::::*_____*:...:::::::..\\\+++++***|____********___/**+++++***********+|:::
  \\++++++++++\\\::::.::*::**\__________/..:::::______________________******:\\***+++++***___________*+++++++************+|.::
   \\+++++++++++\\\*::.::..:::::_:::::::*/________++*+++++**********__________/++++++++++++++++++++++++++++++++++******++//..:
     \\+++++++++++\\_____:::::::/________/*+++++++++++**++++++***********++++++++++++++++++++++++++++++++++++++++***+++//....:
      \\\+++++++++++++++________/+++++++++***++++++++++++++++++++++++++++***++++++++++++++++++++++++**+++++++*******+//.......
        \\\++++++++++++++++++++***++++++++++***++++++++++++++++++++++++++++++++++++++++++++++++++++++++++**********+//........
          \\\++++++++++++++++++++**++++++++++***++++++++++++++++++++++++++++++++++++++++++++++++++++++***********+///.........
            \\\\++++*++++++++++++***+++++++++++***++++++++++++++++++++++++++++++++++++*++++++++++++**********++//// ..........
                \___++++++++++++++***++++++++++++***+++++++++++++++*++++++++++++++++++++****************+++__///  ............
                    \\\\++++++++++****++++++++++++****+++++++++++++++****++++++++++++++++*************++////        ..........
                        \\__++++++******++++++++++++****+++++++++++++*********+++++++++++*********+++////      .  ............
                            _____++++++++++++++++++*********+++++++++*****************++++++++++____/         ................
                                 __________*+++++++++**********++++++++***********+++++_________          ....................
                                          _________*++++++++++++++****+++++++++_________               .......................
                                                  ______________________________                       .......................
                                                                                                      ........................
                                                                                                   ...........................
```
</details>

## Install
🚧 WIP 🚧

## Usage
🚧 WIP 🚧
