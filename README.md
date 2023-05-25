`gut:`
```js
$($private)._getAnimationTimeline = function ()
{
    return this._fAnimationTimeline_gut || this._initAnimationTimeline();
}

$($private)._initAnimationTimeline = function ()
{
    /*debug_code_block_to_be_removed_by_release_builder...*/
    if (this._fAnimationTimeline_gut)
    {
        this.__throwException("Instance already exist!", this._initAnimationTimeline);
    }
    /*...debug_code_block_to_be_removed_by_release_builder*/

    var l_gut = this._fAnimationTimeline_gut = new GUTimeline();
    l_gut.i_callHandlerAtTime(0, this._someHandler.i_toObjectMethod(this));

    return l_gut;
    /* Move the following import to the IL DEPENDENCIES section if needed */
    /* var GUTimeline = module_ns.gunified_ns.g_extensions_ns.view_ns.tools_ns.i_importGUTimelineClass(); */
}

$($private)._someHandler = function ()
{
    
}
```

`gute:`

```js
$($private)._getAnimationTimeline = function ()
{
    return this._fAnimationTimeline_gut || this._initAnimationTimeline();
}

$($private)._initAnimationTimeline = function ()
{
    /*debug_code_block_to_be_removed_by_release_builder...*/
    if (this._fAnimationTimeline_gut)
    {
        this.__throwException("Instance already exist!", this._initAnimationTimeline);
    }
    /*...debug_code_block_to_be_removed_by_release_builder*/

    var l_gut = this._fAnimationTimeline_gut = new GUTimeline();
    l_gut.i_addEventListener(GUTimeline.i_EVENT_ANIMATION_COMPLETED, this._onAnimationCompleted.i_toEventlessHandler(this));
    l_gut.i_callHandlerAtTime(0, this._someHandler.i_toObjectMethod(this));

    return l_gut;
    /* Move the following import to the IL DEPENDENCIES section if needed */
    /* var GUTimeline = module_ns.gunified_ns.g_extensions_ns.view_ns.tools_ns.i_importGUTimelineClass(); */
}

$($private)._onAnimationCompleted = function ()
{
    
}

$($private)._someHandler = function ()
{
    
}
```

`ust:`

```js
$($private)._getAnimationTimer = function ()
{
    return this._fAnimationTimer_ust || this._initAnimationTimer();
}

$($private)._initAnimationTimer = function ()
{
    /*debug_code_block_to_be_removed_by_release_builder...*/
    if (this._fAnimationTimer_ust)
    {
        this.__throwException("Instance already exist!", this._initAnimationTimer);
    }
    /*...debug_code_block_to_be_removed_by_release_builder*/

    var l_ust = this._fAnimationTimer_ust = new USimpleTimer(1 / 30, 10, false, this.i_getCStage().i_getFrameEnteringTimer(), true);
    l_ust.i_addEventListener(USimpleTimer.i_EVENT_COMPLETED, this._onAnimationTimerCompleted.i_toEventlessHandler(this));
    l_ust.i_addEventListener(USimpleTimer.i_EVENT_TICK, this._onAnimationTimerTick.i_toEventHandler(this));
    return l_ust;
    /* Move the following import to the IL DEPENDENCIES section if needed */
    /* var USimpleTimer = module_ns.unified_ns.controller_ns.time_ns.i_importUSimpleTimerClass(); */
}

$($private)._onAnimationTimerCompleted = function ()
{
    console.log("onAnimationTimerCompleted")
}

$($private)._onAnimationTimerTick = function (aEvent_ue)
{
    var lTicksCount_int = aEvent_ue.i_getEventDispatcher().i_getElapsedTicksCount();
    console.log(lTicksCount_int)
}
```

`ut:`

```js
$($private)._getAnimationTween = function ()
{
    return this._fAnimationTween_ut || this._initAnimationTween();
}

$($private)._initAnimationTween = function ()
{
    /*debug_code_block_to_be_removed_by_release_builder...*/
    if (this._fAnimationTween_ut)
    {
        this.__throwException("Instance already exist!", this._initAnimationTween);
    }
    /*...debug_code_block_to_be_removed_by_release_builder*/

    var l_ut = this._fAnimationTween_ut = new UTween(this._someReciever.i_toObjectMethod(this), UTween.i_LINEAR, 0, 1, 30 / 30, this.i_getCStage().i_getFrameEnteringTimer());
    l_ut.i_addEventListener(UTween.i_EVENT_TWEENING_COMPLETED, this._onAnimationTweenCompleted.i_toEventHandler(this));
    return l_ut;
    /* Move the following import to the IL DEPENDENCIES section if needed */
    /* var UTween = module_ns.unified_ns.controller_ns.base_ns.transitions_ns.i_importUTweenClass(); */
}

$($private)._onAnimationTweenCompleted = function ()
{
    console.log("onAnimationTweenCompleted")
}
```

`guqa:`

```js
$($private)._getAnimationQueue = function ()
{
    return this._fAnimationQueue_guqa || this._initAnimationQueue();
}

$($private)._initAnimationQueue = function ()
{
    /*debug_code_block_to_be_removed_by_release_builder...*/
    if (this._fAnimationQueue_guqa)
    {
        this.__throwException("Instance already exist!", this._initAnimationQueue);
    }
    /*...debug_code_block_to_be_removed_by_release_builder*/

    var l_guqa = this._fAnimationQueue_guqa = new GUQueueAnimation();
    l_guqa.i_initReceiver(this.i_setScale.i_toObjectMethod(this));
    l_guqa.i_callHandler(this._someHandler.i_toObjectMethod(this));
    l_guqa.i_tweenValueTo(2, 5);
    l_guqa.i_waitNextTween(5);
    l_guqa.i_tweenValueTo(1, 5);

    return l_guqa;
    /* Move the following import to the IL DEPENDENCIES section if needed */
    /* var GUQueueAnimation = module_ns.gunified_ns.g_extensions_ns.view_ns.tools_ns.i_importGUQueueAnimationClass(); */
}

$($private)._someHandler = function ()
{
    
}
```

`udo:`

```js
$($private)._getAssetView = function ()
{
    return this._fAssetView_udo || this._initAssetView()
}

$($private)._initAssetView = function ()
{
    /*debug_code_block_to_be_removed_by_release_builder...*/
    if (this._fAssetView_udo)
    {
        this.__throwException("Instance already exist!", this._initAssetView);
    }
    /*...debug_code_block_to_be_removed_by_release_builder*/

    var l_gmrsl = GMain.i_getInstance().i_getPreloadingController().i_getResourcesLoader();
    var l_udo = this._fAssetView_udo = new ULoader(l_gmrsl.i_getAssetViewImgURL(), false, null, l_gmrsl).i_getContent();
    l_udo.i_alignLocalBoundsCM();
    l_udo.i_setAdditiveBlendingMode();
    l_udo.i_setXY(0, 0);
    l_udo.i_setScale(1);
    l_udo.i_setAlpha(1);
    l_udo.i_setRotationInDegrees(0);

    return l_udo;
    /* Move the following import to the IL DEPENDENCIES section if needed */
    /* var ULoader = module_ns.unified_ns.view_ns.base_ns.display_ns.i_importULoaderClass(); */
    /* var GMain = module_ns.controller_ns.main_ns.i_importGMainClass(); */
}
```
