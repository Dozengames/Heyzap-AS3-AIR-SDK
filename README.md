Heyzap-AS3-AIR-SDK
==================

Heyzap check-in main timeline AS3 AIR SDK

//First frame of the Main timeline

import com.heyzap.extensions.*;

import flash.events.MouseEvent;
  import flash.text.TextField;
	import flash.desktop.NativeApplication;
	import flash.events.Event;
	import flash.events.StatusEvent;
	import flash.display.Sprite;
	import flash.display.StageAlign;
	import flash.display.StageScaleMode;
	import flash.text.TextFieldAutoSize;
	import flash.text.TextFormat;
	import flash.ui.Multitouch;
	import flash.ui.MultitouchInputMode;
	
	import com.heyzap.extensions.Heyzap;
	
	var h : Heyzap;

//Insert where You want to call heyzap check-in funktion
//Use heyzap button 
heyzap.addEventListener(MouseEvent.CLICK,Main);
		
	function Main(event:MouseEvent)
		{
			stage.scaleMode = StageScaleMode.NO_SCALE;
			stage.align = StageAlign.TOP_LEFT;
			stage.addEventListener(Event.DEACTIVATE, deactivate);
			Multitouch.inputMode = MultitouchInputMode.TOUCH_POINT;

			// Load heyzap and show the checkin screen
			h = new Heyzap();
			h.load(true, "123456", "mycoolscheme");
			h.checkin("Im playing Floors Escape! Its really cool and I think you would like it!");
		
		}
		
		function deactivate(e:Event):void 
		{
			// NOTE: Do not quit the application, Heyzap.checkin() will also deactivate the app and thus quit it if you leave this line in
			// auto-close
			//NativeApplication.nativeApplication.exit();
		}	
