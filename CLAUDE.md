# Dynamic Price Flow - TradingView Project

## 🎯 Project Vision

Create a **real-time options flow lower indicator** for TradingView that leverages actual options volume data to provide superior 0DTE trading signals, moving beyond synthetic price-momentum proxies to true options market sentiment analysis.

## 🚨 **PROJECT STATUS: ✅ STRATEGIC EXTRACTION APPROACH VALIDATED - V2 DEVELOPMENT APPROVED**
**✅ MAJOR MILESTONE: External code review validates Strategic Extraction approach for V2**

**Last Updated**: December 18, 2025  
**Current Version**: Options_Flow_Engine_v2.pine (STRATEGIC EXTRACTION IMPLEMENTATION)  
**Status**: **PHASE 0 COMPLETE** - Strategic Extraction approach externally validated, V2 framework created

### 🎯 **DECEMBER 18, 2025 SESSION ACCOMPLISHMENTS**
- **✅ EXTERNAL CODE REVIEW COMPLETE** - Strategic Extraction approach validated by external Claude reviewer
- **✅ GEMINI AI PLANNER VALIDATION** - Comprehensive roadmap approved by AI planner
- **✅ ROOT CAUSE ANALYSIS** - V1 failure identified as insufficient infrastructure extraction
- **✅ V2 FRAMEWORK CREATED** - Options_Flow_Engine_v2.pine with Strategic Extraction architecture
- **✅ PROJECT REORGANIZATION** - V1 archived, comprehensive todo list created
- **✅ IMPLEMENTATION ROADMAP** - 17-task roadmap spanning 3 phases approved

### 📋 **VALIDATED V2 APPROACH: Strategic Extraction**
**Key Insight**: V1 failed due to cherry-picking functions without dependency chain
**Solution**: Copy entire working infrastructure (6000+ lines) from Options Volume Profile and modify
**Validation**: ✅ External reviewer confirmed line numbers and approach correctness
**Request Budget**: ✅ 38/40 requests validated as optimal (19 strikes × 2 sides)

### ✅ **DECEMBER 17, 2025 SESSION ACCOMPLISHMENTS**
- **✅ Fixed timeframe validation error** - Changed from "1m" to chart timeframe
- **✅ Implemented proper request limit management** - Safe 38/40 request usage
- **✅ Added critical safeguards from original options volume profile**
- **✅ WORKING INDICATOR** - Successfully compiles and displays flow data
- **✅ Distance-weighted flow calculation** - Real options volume, not synthetic
- **✅ Session reset logic** - Proper 9:30 AM ET reset mechanism

### 📋 **CURRENT WORKING FEATURES**
- **✅ 19-strike range** (ATM ±9) with gamma-based distance weighting
- **✅ Real-time volume data** - Actual call/put contract volumes  
- **✅ Session cumulative flow** - Resets at market open
- **✅ Multiple visualization layers** - Main flow, delta, zero line
- **✅ Comprehensive debugging** - Volume statistics and validation

### 🚨 **V1 CRITICAL ISSUE: Session Persistence (SOLVED IN V2)**
**V1 Problem**: TradingView refresh resets cumulative flow (loses 9:30AM-current data)
**V1 Impact**: Makes indicator unreliable for actual 0DTE trading
**V2 Solution**: Strategic Extraction includes proven session management + checkpoint system

### 📋 **V2 STRATEGIC EXTRACTION IMPLEMENTATION ROADMAP**
**✅ EXTERNALLY VALIDATED BY CLAUDE CODE REVIEWER + GEMINI AI PLANNER**

#### **PHASE 0: PROJECT SETUP** ✅ (COMPLETED - December 18, 2025)
**Objective**: Organize project structure and prepare for Strategic Extraction
- [x] **0.1: V2 Framework Creation** - ✅ DONE: Options_Flow_Engine_v2.pine created
- [x] **0.2: V1 Archival** - ✅ DONE: Failed V1 moved to archive folder
- [x] **0.3: Documentation Update** - ✅ DONE: CLAUDE.md updated with validated approach

**Success Metrics**: ✅ Project organized, V2 framework ready, approach documented

#### **PHASE 1: STRATEGIC INFRASTRUCTURE EXTRACTION** 🔧 (NEXT PRIORITY)
**Objective**: Copy complete working infrastructure from Options Volume Profile
- [ ] **1.1: Core Infrastructure** - Copy lines 1-500 (ALL arrays, variables, inputs)
- [ ] **1.2: Utility Functions** - Copy lines 1080-1110 (roundToNearest, getOptionSymbol, timezone)
- [ ] **1.3: Strike Building Engine** - Copy lines 1287-1445 (complete f_buildStrikes function)
- [ ] **1.4: Initialization Logic** - Copy lines 1468-1485 (listReady state, reference tracking)
- [ ] **1.5: Volume Fetching Engine** - Copy lines 1534-1650 (complete request.security implementation)
- [ ] **1.6: Phase 1 Validation** - Compilation test, strike generation (19 strikes), volume loading (>80% success)

**Success Metrics**: Indicator compiles, 19 strikes generate correctly, volume data loads reliably

#### **PHASE 2: FLOW CALCULATION ENGINE** 📈 (AFTER PHASE 1)
**Objective**: Implement distance-weighted flow calculation with session tracking
- [ ] **2.1: Distance Weighting System** - getStrikeWeight function (ATM=100%, Near=80%, OTM=40%, Deep=10%)
- [ ] **2.2: Flow Calculation Core** - calculateWeightedFlow function with (callVol - putVol) × weight
- [ ] **2.3: Session Cumulative Tracking** - sessionCumulativeFlow variable with 9:30 AM ET resets
- [ ] **2.4: Phase 2 Validation** - Flow direction correlation, session reset testing, weight verification

**Success Metrics**: Flow correlates with market sentiment, session resets work, weighting validated

#### **PHASE 3: SESSION PERSISTENCE & VISUALIZATION** 🎮 (FINAL PHASE)
**Objective**: Solve session persistence challenge and add production visualization
- [ ] **3.1: Session Persistence** - Refresh detection, volume reconstruction, checkpoint system (15-min intervals)
- [ ] **3.2: Flow Visualization** - Basic flow line plot (green/red), zero reference line, color coding
- [ ] **3.3: Comprehensive Testing** - Multi-symbol (SPX/SPY/QQQ), market conditions, edge cases, persistence testing
- [ ] **3.4: Final Validation** - Performance (<2s load), accuracy validation, request budget (<38/40), memory usage

**Success Metrics**: Flow survives TradingView refresh, production-ready performance, trading reliability

### 📋 **LEGACY V1 ROADMAP (ARCHIVED)**

#### **PHASE 1: FOUNDATION VALIDATION** ✅ (COMPLETED)
**Objective**: Confirm compilation fixes work and basic functionality operates
- [x] **1.1: Compilation Test** - ✅ DONE: Loads without errors
- [x] **1.2: Strike Generation Test** - ✅ DONE: 19 strikes generating properly
- [x] **1.3: Data Loading Test** - ✅ DONE: Volume data loading successfully
- [x] **1.4: Basic Plot Test** - ✅ DONE: Flow lines displaying correctly

**Success Metrics**: ✅ <2 sec load time, flow visualization working, request limits respected

#### **PHASE 1.5: SESSION PERSISTENCE** 🚨 (URGENT - NEXT PRIORITY)
**Objective**: Solve TradingView refresh data loss issue
- [ ] **1.5.1: Session Volume Reconstruction** - Query historical volume from 9:30 AM
- [ ] **1.5.2: Flow State Recovery** - Rebuild cumulative flow after refresh
- [ ] **1.5.3: Checkpoint System** - Store flow snapshots every 30 minutes  
- [ ] **1.5.4: Testing** - Verify persistence across manual refresh

**Success Metrics**: Flow line survives TradingView refresh, maintains session accuracy

#### **PHASE 2: CORE FUNCTIONALITY** 🔧  
**Objective**: Validate flow calculations and session logic work correctly
- [ ] **2.1: Weight Distribution Test** - Verify ATM gets 1.0 weight, decreases properly
- [ ] **2.2: Flow Calculation Test** - Confirm weighted call-put math is accurate  
- [ ] **2.3: Session Reset Test** - Verify 9:30 AM reset works across multiple days
- [ ] **2.4: Real-time Updates** - Test flow responds to actual market activity

**Success Metrics**: Flow direction correlates with obvious sentiment, resets work perfectly

#### **PHASE 3: SIGNAL OPTIMIZATION** 📈
**Objective**: Add divergence detection and trading signals  
- [ ] **3.1: Divergence Engine** - Build price vs flow comparison logic
- [ ] **3.2: Alert System** - Create actionable 0DTE trading signals
- [ ] **3.3: Threshold Tuning** - Optimize signal sensitivity vs noise
- [ ] **3.4: Multi-timeframe** - Add flow acceleration and momentum

**Success Metrics**: Clear signals on historical high-probability setups

## 📊 Original State Analysis

### Available Resources
1. **Options Volume Profile (6000+ lines)** - Full options data access framework
2. **ThinkScript Dynamic Flow** - Synthetic flow using price momentum  
3. **GEX Enhanced v4** - Gamma exposure and pin risk analysis
4. **Gemini AI Recommendations** - Distance-weighted volume approach

### Key Insight: Real vs Synthetic Data
- **ThinkScript Limitation**: Uses price movement as proxy for flow (price up = "call buying")
- **TradingView Advantage**: Direct access to actual options contract volumes via `request.security`
- **Opportunity**: Build true flow indicator using real volume data

## 🚀 Project Goals

### Primary Objective
Create a **session-based cumulative options flow indicator** that:
- Resets at market open (9:30 AM ET)
- Uses actual call/put volume data  
- Weights strikes by distance from ATM (gamma proximity)
- Provides actionable signals for 0DTE trading

### Success Metrics
- Superior signal quality vs synthetic approaches
- Clear divergence detection (price vs flow)
- Reduced false signals during key trading hours
- Real-time sentiment shifts for 0DTE timing

## 🏗️ Technical Architecture

### Core Data Pipeline
```
Options Contracts → Volume Extraction → Distance Weighting → Flow Calculation → Visualization
```

### Strike Classification System
- **ATM Zone** (±2 strikes): 100% weight - "Zone of Battle"
- **Near Money** (±5 strikes): 70% weight - "Directional Commitment"  
- **OTM Hedges** (>5 strikes): 20% weight - "Noise/Insurance"

### Flow Calculation Framework
```pinescript
// Conceptual Formula
netFlow = Σ(callVolume * strikeWeight) - Σ(putVolume * strikeWeight)
where strikeWeight = f(distanceFromATM, timeToExpiry)
```

## 📈 Indicator Design Specification

### Visual Components

#### 1. Primary Flow Line (Main Signal)
- **Calculation**: Cumulative Net Delta (weighted calls - weighted puts)
- **Reset**: 9:30 AM ET daily
- **Color**: Green when positive, Red when negative
- **Key Signal**: Slope direction and divergences with price

#### 2. Total Energy Histogram (Volume Context) 
- **Calculation**: Total Call Vol + Total Put Vol (all strikes)
- **Purpose**: Measure volatility/battle intensity
- **Alert Logic**: High energy + flat flow = imminent breakout

#### 3. Gamma Flip Background (Bias Filter)
- **Calculation**: ATM Calls vs ATM Puts comparison
- **Visual**: Background tint (Green = Call dominance, Red = Put dominance)
- **Purpose**: Institutional bias indicator

#### 4. Smart Divergence Alerts
- **Price Higher High + Flow Lower High** = Bearish divergence
- **Price Lower Low + Flow Higher Low** = Bullish divergence
- **Visual**: Arrows or background color changes

### Advanced Features (Phase 2)

#### Split Flow Analysis
- **Speculative Flow**: OTM Call/Put ratio (retail sentiment)
- **Institutional Flow**: ITM Call/Put ratio (smart money)
- **Signal Generation**: Alignment vs divergence between flows

#### Time-Weighted Intensity
- **Morning Session**: Standard weighting
- **Power Hour**: 1.5x gamma multiplier (2-4 PM)
- **Final 30 Minutes**: 2x multiplier (maximum pin risk)

## 🎯 Implementation Strategy

### Phase 1: Core Flow Engine (MVP)
**Goal**: Basic real-time flow tracking
**Components**:
- Extract volumes from 9 strikes (ATM ±4)
- Implement distance weighting
- Create cumulative flow line
- Add session reset logic

**Estimated Effort**: ~200 lines (vs 6000 in volume profile)

### Phase 2: Advanced Analytics  
**Goal**: Sophisticated signal generation
**Components**:
- Add divergence detection
- Implement energy histogram
- Create gamma flip background
- Build alert system

### Phase 3: Integration & Optimization
**Goal**: Production-ready tool
**Components**:
- Integrate with existing GEX data
- Add user customization options
- Optimize performance
- Create documentation

## 📚 Code Library & Building Blocks

### Key Functions from Options Volume Profile (Lines 1287-1445)

#### Strike Generation Logic
```pinescript
// Build strike list around reference price
f_buildStrikes(_anchor) =>
    // Clear existing arrays
    array.clear(callSyms), array.clear(putSyms)
    array.clear(callVols), array.clear(putVols)
    array.clear(strikePrices)
    
    // Centre strike using rounding
    strikeVal = roundToNearest(_anchor, effectiveRoundStrike)
    array.push(strikePrices, strikeVal)
    
    // Add strikes above and below
    for i = 1 to numStrikesAbove
        s = strikeVal + i * effectiveSpacing
        array.push(strikePrices, s)
    for i = 1 to numStrikesBelow  
        s = strikeVal - i * effectiveSpacing
        array.push(strikePrices, s)
```

#### Options Symbol Format (Lines 1081-1112)
```pinescript
getOptionSymbol(_under, _yr, _mo, _dy, _side, _strike) =>
    base = _under
    adjusted_strike = effectiveIsSpx ? math.round(_strike / spxRounding) * spxRounding : _strike
    yy = str.format("{0,number,00}", _yr % 100)
    mm = str.format("{0,number,00}", _mo)  
    dd = str.format("{0,number,00}", _dy)
    
    if effectiveIsSpx
        strikeStr = str.tostring(adjusted_strike, "#") + ".0"
        base + yy + mm + dd + _side + strikeStr
    else
        // Regular options formatting
        strikeStr = str.tostring(adjusted_strike)
        base + yy + mm + dd + _side + strikeStr
```

#### Volume Data Retrieval (Lines 1534-1578)
```pinescript
// Core volume fetching loop
if listReady
    for j = 0 to array.size(strikePrices)-1
        for side = 0 to 1
            sym = side == 0 ? array.get(callSyms,j) : array.get(putSyms,j)
            [vol, price] = request.security(sym, volTF, [volume, close], 
                                          gaps = barmerge.gaps_off, 
                                          lookahead = barmerge.lookahead_on, 
                                          ignore_invalid_symbol = true)
            
            safeVol = na(vol) ? 0.0 : vol
            
            if side == 0
                array.set(callVols, j, safeVol)
            else  
                array.set(putVols, j, safeVol)
```

#### Session Reset Logic (Lines 1482-1490)
```pinescript
// Daily refresh at 09:30 ET
if isRthOpen and isToday and not (hour == 9 and minute == 30)
    referencePrice := getReferencePrice()
    if referencePrice != anchorOpen
        anchorOpen := referencePrice
    openingBarIndex := bar_index
    f_buildStrikes(anchorOpen)  // Rebuild strikes
    marketOpenPrice := open
```

### Distance Weighting Framework

#### Strike Distance Calculation
```pinescript
// Calculate distance from ATM for weighting
getStrikeWeight(strikePrice, currentPrice, maxDistance) =>
    distance = math.abs(strikePrice - currentPrice)
    if distance <= 1 * strikeSpacing  // ATM zone
        1.0  // 100% weight
    else if distance <= 2 * strikeSpacing  // Near money
        0.8  // 80% weight  
    else if distance <= 4 * strikeSpacing  // OTM
        0.4  // 40% weight
    else
        0.1  // Deep OTM - minimal weight
```

### ThinkScript Session Logic (Lines 126-135, 164-166)

#### Sentiment State Tracking
```thinkscript
// Track sentiment persistence  
def sentimentState;
if callsCrossAbovePuts {
    sentimentState = 1;    // Bullish
} else if callsCrossBelowPuts {
    sentimentState = -1;   // Bearish  
} else if IsNaN(sentimentState[1]) {
    sentimentState = 0;    // Neutral
} else {
    sentimentState = sentimentState[1];  // Hold previous
}
```

#### Session Reset Pattern
```thinkscript
// Regular market hours check
def isRegularHours = secondsFromTime(0435) >= 0 and secondsTillTime(1945) > 0;

// Session-based plotting
plot plotNetFlow = if isRegularHours then calculatedFlow else Double.NaN;
```

### Flow Calculation Engine (NEW - To Build)

#### Core Flow Formula
```pinescript
// Weighted net flow calculation
calculateNetFlow(callVols, putVols, strikePrices, currentPrice) =>
    netFlow = 0.0
    for i = 0 to array.size(strikePrices) - 1
        strike = array.get(strikePrices, i)
        weight = getStrikeWeight(strike, currentPrice, maxStrikesFromPrice)
        callVol = array.get(callVols, i) 
        putVol = array.get(putVols, i)
        netFlow := netFlow + (callVol - putVol) * weight
    netFlow
```

#### Cumulative Flow Tracking
```pinescript
// Session cumulative flow (resets daily)
var float sessionCumulativeFlow = 0.0
var float previousBarFlow = 0.0

// Reset at market open
if hour == 9 and minute == 30
    sessionCumulativeFlow := 0.0
    previousBarFlow := 0.0

// Calculate current bar flow
currentFlow = calculateNetFlow(callVols, putVols, strikePrices, close)
flowDelta = currentFlow - previousBarFlow
sessionCumulativeFlow := sessionCumulativeFlow + flowDelta
previousBarFlow := currentFlow
```

### Advanced Analytics Components

#### Flow Divergence Detection  
```pinescript
// Price vs Flow divergence
detectDivergence(priceHigh, priceLow, flowHigh, flowLow, lookback) =>
    // Bullish divergence: Price lower low, Flow higher low
    bullishDiv = priceLow < priceLow[lookback] and flowLow > flowLow[lookback]
    
    // Bearish divergence: Price higher high, Flow lower high  
    bearishDiv = priceHigh > priceHigh[lookback] and flowHigh < flowHigh[lookback]
    
    [bullishDiv, bearishDiv]
```

#### Volume Energy Calculation
```pinescript
// Total options energy (volatility context)
calculateTotalEnergy(callVols, putVols) =>
    totalEnergy = 0.0
    for i = 0 to array.size(callVols) - 1
        totalEnergy := totalEnergy + array.get(callVols, i) + array.get(putVols, i)
    totalEnergy
```

### Essential Utility Functions

#### Time & Session Management (From Options Volume Profile Lines 230-233)
```pinescript
// Time variables for session management
isRthOpen = (hour == 9 and minute == 30)
isToday = (dayofmonth == effectiveDay and month == effectiveMonth and year == effectiveYear)
labelOffset = barstate.isconfirmed ? 0 : 1

// Market hours check
isRegularHours = (hour >= 9 and hour < 16) or (hour == 16 and minute == 0)
```

#### Strike Rounding & Spacing (Lines 1070-1078)
```pinescript
// Handle decimal strikes properly for different instruments
roundToNearest(v, nearest) =>
    multiplier = 10.0
    baseStrike = math.round(v / baseStrikePattern) * baseStrikePattern
    result = math.round(baseStrike / nearest) * nearest
    math.round(result * multiplier) / multiplier
```

#### Auto-Detection Logic (Lines 199-204)
```pinescript
// Auto-detect SPX and set appropriate parameters
autoDetectedSPX = syminfo.ticker == "SPX"
tickerSymbol = autoDetectedSPX ? "SPXW" : syminfo.ticker
effectiveIsSpx = autoDetectedSPX or syminfo.ticker == "SPXW"
effectiveRoundStrike = effectiveIsSpx ? 10 : 1  // SPX uses 10-point rounding
effectiveSpacing = effectiveIsSpx ? 10 : 1      // SPX uses 10-point spacing
```

### Volume Delta Calculation (From Options Volume Profile Lines 1593-1620)
```pinescript
// Calculate volume delta with previous bar tracking
calcVolumeDelta(callVol, putVol) =>
    callVol - putVol

// Track delta changes between bars
updateVolumeDeltas(j, currentDelta, confirmedDeltas, deltaChanges) =>
    if array.size(confirmedDeltas) > j
        confirmedDelta = array.get(confirmedDeltas, j)
        currentChange = currentDelta - confirmedDelta
        array.set(deltaChanges, j, currentChange)
        
        // Update confirmed values on bar confirmation
        if barstate.isconfirmed
            array.set(confirmedDeltas, j, currentDelta)
```

### Visualization Framework

#### Multi-Layer Plot Structure
```pinescript
// Layer 1: Primary flow line
plot netFlowLine = sessionCumulativeFlow
netFlowLine.color = sessionCumulativeFlow > 0 ? color.green : color.red

// Layer 2: Energy histogram  
plot energyBars = calculateTotalEnergy(callVols, putVols)
energyBars.color = color.new(color.gray, 70)
energyBars.style = plot.style_histogram

// Layer 3: Background bias
bgcolor(atmCallVol > atmPutVol ? color.new(color.green, 90) : color.new(color.red, 90))
```

#### Alert System Framework
```pinescript
// Divergence alerts
alertcondition(bullishDivergence, title="Bullish Flow Divergence", 
              message="Price making lower lows while flow making higher lows")
              
alertcondition(bearishDivergence, title="Bearish Flow Divergence", 
              message="Price making higher highs while flow making lower highs")
              
// Flow momentum alerts  
alertcondition(flowAcceleration > accelerationThreshold, title="Strong Bullish Flow", 
              message="Options flow showing strong bullish acceleration")
```

### Data Structure Templates

#### Array Initialization Pattern
```pinescript
// Core data arrays (from Options Volume Profile structure)
var string[] callSyms = array.new_string()
var string[] putSyms = array.new_string()
var float[] callVols = array.new_float()
var float[] putVols = array.new_float() 
var float[] strikePrices = array.new_float()

// Flow calculation arrays
var float[] confirmedDeltas = array.new_float()
var float[] deltaChanges = array.new_float()
var float[] strikeWeights = array.new_float()

// Clear arrays function
clearArrays() =>
    array.clear(callSyms), array.clear(putSyms)
    array.clear(callVols), array.clear(putVols)
    array.clear(strikePrices)
```

## 🏗️ RIGOROUS DEVELOPMENT PROCESS

### Strike Range Specification
**Target: 19 Total Strikes (ATM ±9)**
- **TradingView Limit**: 40 requests maximum
- **Our Usage**: 19 strikes × 2 sides = 38 requests (95% capacity utilization)
- **Buffer**: 2 requests remaining for error handling/debugging
- **Range Logic**: ATM ±9 captures full gamma spectrum without artificial limitations

### Strike Weight Distribution (19 Strikes)
```pinescript
// Optimized for 19-strike range
getStrikeWeight(strikePrice, currentPrice, strikeSpacing) =>
    distance = math.abs(strikePrice - currentPrice)
    if distance == 0                               // ATM
        1.0     // 100% weight - maximum impact
    else if distance <= 1 * strikeSpacing         // ±1 strike  
        0.9     // 90% weight - high gamma
    else if distance <= 2 * strikeSpacing         // ±2 strikes
        0.75    // 75% weight - significant gamma
    else if distance <= 3 * strikeSpacing         // ±3 strikes  
        0.6     // 60% weight - moderate gamma
    else if distance <= 5 * strikeSpacing         // ±4-5 strikes
        0.4     // 40% weight - lower gamma but still relevant
    else if distance <= 7 * strikeSpacing         // ±6-7 strikes
        0.25    // 25% weight - hedging/speculation
    else                                           // ±8-9 strikes
        0.1     // 10% weight - extreme OTM (noise filter)
```

## 🛠️ STEP-BY-STEP DEVELOPMENT METHODOLOGY

### ⚠️ CRITICAL RULE: Never Skip Validation Steps
**Build → Test → Validate → Document → Proceed**

---

## 📋 PHASE 1: FOUNDATION (Core Data Pipeline)

### Step 1.1: Basic Structure Setup
**Objective**: Create minimal working framework
**Time Estimate**: 30 minutes

#### Tasks:
- [ ] Copy Pine Script v6 header and basic indicator setup
- [ ] Add user inputs for basic parameters (strikes, timeframe, symbol)
- [ ] Initialize core arrays for 19 strikes
- [ ] Add session time detection logic

#### Code Blocks to Implement:
```pinescript
//@version=6
indicator("Options Flow Engine v1.0", shorttitle="OFE", overlay=false)

// Core inputs
numStrikesAbove = 9
numStrikesBelow = 9  
volTF = "1m"
```

#### ✅ Validation Checkpoint 1.1:
- [ ] **Compiles without errors** 
- [ ] **Shows in TradingView lower panel**
- [ ] **Displays basic inputs properly**
- [ ] **Time detection works correctly** (test with different hours)

**🚫 STOP: Do not proceed until all checkboxes are confirmed**

---

### Step 1.2: Strike Generation Engine  
**Objective**: Build robust strike list around current price
**Time Estimate**: 45 minutes

#### Tasks:
- [ ] Implement `roundToNearest()` function for strike rounding
- [ ] Build `f_buildStrikes()` with 19-strike capability  
- [ ] Add SPX auto-detection and formatting logic
- [ ] Create strike price validation system

#### Code Implementation:
```pinescript
// Use exact code from Lines 123-142 in CLAUDE.md
// Modify loop ranges:
for i = 1 to 9  // numStrikesAbove = 9
for i = 1 to 9  // numStrikesBelow = 9
```

#### ✅ Validation Checkpoint 1.2:
- [ ] **19 strikes generated correctly around current price**
- [ ] **SPX strikes use 10-point increments** (test with SPXW)
- [ ] **Regular stocks use appropriate increments** (test with SPY, QQQ)
- [ ] **Strike prices make mathematical sense** (no duplicates, proper spacing)
- [ ] **Edge cases handled** (market open, price gaps, weekends)

**📊 Test Data**: Run on SPX, SPY, QQQ, AAPL - verify strike generation logic

**🚫 STOP: Manually verify strike generation accuracy before proceeding**

---

### Step 1.3: Options Symbol Formation
**Objective**: Create correct options symbols for data retrieval
**Time Estimate**: 30 minutes  

#### Tasks:
- [ ] Implement `getOptionSymbol()` with proper formatting
- [ ] Add current date logic for 0DTE detection
- [ ] Handle SPX vs regular options formatting differences
- [ ] Add symbol validation logging

#### Code Implementation:
```pinescript
// Use Lines 145-160 from CLAUDE.md
// Add debug logging:
if barstate.islast and barstate.isconfirmed
    log.info("Sample call symbol: " + array.get(callSyms, 0))
    log.info("Sample put symbol: " + array.get(putSyms, 0))
```

#### ✅ Validation Checkpoint 1.3:
- [ ] **Symbols format correctly** (check Pine Script logs)
- [ ] **SPX symbols use SPXW prefix**
- [ ] **Date formatting correct** (YYMMDD pattern)
- [ ] **Call/Put suffixes correct** ("C" and "P")
- [ ] **Strike formatting matches TradingView conventions**

**🔍 Manual Verification**: Copy generated symbols and verify they exist in TradingView

**🚫 STOP: Confirm at least 5 symbols manually resolve in TradingView**

---

### Step 1.4: Volume Data Retrieval
**Objective**: Successfully fetch volume data for all 19 strikes  
**Time Estimate**: 60 minutes

#### Tasks:
- [ ] Implement core `request.security()` loop
- [ ] Add error handling for invalid symbols
- [ ] Track data loading status
- [ ] Implement volume validation logic

#### Code Implementation:
```pinescript
// Use Lines 164-180 from CLAUDE.md  
// Add request monitoring:
var int successfulRequests = 0
var int failedRequests = 0

// Track request success rate
if not na(vol)
    successfulRequests := successfulRequests + 1
else  
    failedRequests := failedRequests + 1
```

#### ✅ Validation Checkpoint 1.4:
- [ ] **Volume data loading for active strikes** (>0 volume on liquid options)
- [ ] **Request success rate >80%** (check successfulRequests/total ratio)
- [ ] **No infinite loops or performance issues** 
- [ ] **Error handling works** (test with invalid symbols)
- [ ] **Data updates in real-time** (verify during market hours)

**📈 Performance Test**: Monitor script execution time - should be <2 seconds

**🚫 STOP: Verify actual volume data is loading before proceeding**

---

## 📋 PHASE 2: FLOW CALCULATION ENGINE

### Step 2.1: Distance Weighting Implementation
**Objective**: Apply gamma-based weighting to strike volumes
**Time Estimate**: 45 minutes

#### Tasks:
- [ ] Implement 19-strike weight distribution algorithm
- [ ] Add weight validation and debugging  
- [ ] Create weight visualization for testing
- [ ] Optimize weight calculation performance

#### Code Implementation:
```pinescript
// Use Lines 197-210 from CLAUDE.md with 19-strike weights
// Add weight debugging:
if barstate.islast 
    totalWeight = 0.0
    for i = 0 to array.size(strikePrices) - 1
        weight = getStrikeWeight(array.get(strikePrices, i), close, strikeSpacing)
        totalWeight := totalWeight + weight
    log.info("Total weight distribution: " + str.tostring(totalWeight))
```

#### ✅ Validation Checkpoint 2.1:
- [ ] **Weight distribution makes intuitive sense** (ATM highest, decreases with distance)
- [ ] **Weights sum to reasonable total** (~9-11 for 19 strikes)
- [ ] **Weight calculation performance acceptable** (<1ms per calculation)
- [ ] **Edge cases handled** (price exactly on strike, extreme price movements)

**🧮 Mathematical Verification**: Manually calculate 3-5 weights and verify against function output

**🚫 STOP: Validate weight logic before implementing flow calculation**

---

### Step 2.2: Core Flow Calculation
**Objective**: Calculate weighted net flow from volume data
**Time Estimate**: 60 minutes

#### Tasks:
- [ ] Implement `calculateNetFlow()` function
- [ ] Add flow validation and bounds checking
- [ ] Create flow debugging and logging
- [ ] Test flow calculation accuracy

#### Code Implementation:
```pinescript  
// Use Lines 240-252 from CLAUDE.md
// Add comprehensive debugging:
if barstate.islast
    totalCallVol = 0.0, totalPutVol = 0.0, weightedCallVol = 0.0, weightedPutVol = 0.0
    for i = 0 to array.size(strikePrices) - 1
        callVol = array.get(callVols, i)
        putVol = array.get(putVols, i) 
        weight = getStrikeWeight(array.get(strikePrices, i), close, strikeSpacing)
        totalCallVol := totalCallVol + callVol
        totalPutVol := totalPutVol + putVol
        weightedCallVol := weightedCallVol + (callVol * weight)
        weightedPutVol := weightedPutVol + (putVol * weight)
    
    log.info("Raw Call Vol: " + str.tostring(totalCallVol) + " | Weighted: " + str.tostring(weightedCallVol))
    log.info("Raw Put Vol: " + str.tostring(totalPutVol) + " | Weighted: " + str.tostring(weightedPutVol))
```

#### ✅ Validation Checkpoint 2.2:
- [ ] **Flow values reasonable compared to raw volume** (weighted < raw totals)
- [ ] **Flow direction makes intuitive sense** (high call volume = positive flow)
- [ ] **Flow responds to market movements** (changes during active trading)
- [ ] **No calculation errors or infinities** 
- [ ] **Performance acceptable** (full calculation <5ms)

**📊 Reality Check**: Compare flow direction to obvious market sentiment periods

**🚫 STOP: Verify flow calculation logic before adding cumulative tracking**

---

### Step 2.3: Session Cumulative Flow Tracking
**Objective**: Track cumulative flow with daily resets
**Time Estimate**: 45 minutes

#### Tasks:
- [ ] Implement session reset logic (9:30 AM ET)
- [ ] Add cumulative flow accumulation  
- [ ] Create flow persistence across bars
- [ ] Add session boundary testing

#### Code Implementation:
```pinescript
// Use Lines 254-270 from CLAUDE.md
// Add session boundary logging:
if hour == 9 and minute == 30 and second == 0
    log.info("SESSION RESET - Cumulative Flow Reset to 0")

// Add flow change tracking:
flowChange = currentFlow - previousBarFlow  
if math.abs(flowChange) > 1000  // Significant flow change threshold
    log.info("Large flow change detected: " + str.tostring(flowChange))
```

#### ✅ Validation Checkpoint 2.3:
- [ ] **Session resets work correctly** (test across multiple days)
- [ ] **Cumulative flow accumulates properly** (positive + positive = more positive)
- [ ] **Flow persists across bars correctly** 
- [ ] **Large flow movements logged and explainable**
- [ ] **No memory leaks or performance degradation**

**🕘 Time Test**: Run indicator across weekend/overnight to verify session resets

**🚫 STOP: Confirm session logic before adding visualization**

---

## 📋 PHASE 3: VISUALIZATION & VALIDATION

### Step 3.1: Basic Flow Line Plot
**Objective**: Display cumulative flow as primary indicator line
**Time Estimate**: 30 minutes

#### Tasks:
- [ ] Create main flow line plot
- [ ] Add color coding (green/red for positive/negative)
- [ ] Implement line styling and width
- [ ] Add zero line reference

#### Code Implementation:
```pinescript
// Basic plotting structure
plot mainFlowLine = sessionCumulativeFlow
mainFlowLine.color = sessionCumulativeFlow > 0 ? color.green : color.red
mainFlowLine.linewidth = 2

plot zeroLine = 0
zeroLine.color = color.gray
zeroLine.linewidth = 1
```

#### ✅ Validation Checkpoint 3.1:
- [ ] **Flow line displays correctly in lower panel**
- [ ] **Colors change appropriately** (green above zero, red below)
- [ ] **Line updates in real-time during market hours**
- [ ] **Zero line provides clear reference**
- [ ] **No visual glitches or artifacts**

**👀 Visual Test**: Run during active market hours and verify line responds to market activity

**🚫 STOP: Ensure basic visualization works before adding complexity**

---

### Step 3.2: Comprehensive Testing & Debugging
**Objective**: Validate entire system under various market conditions
**Time Estimate**: 90 minutes

#### Comprehensive Test Suite:

##### Market Condition Tests:
- [ ] **Pre-Market** (7:00-9:30 AM): Should show minimal/no flow
- [ ] **Market Open** (9:30 AM): Should reset cumulative flow
- [ ] **Active Trading** (10:00 AM-12:00 PM): Should show dynamic flow changes  
- [ ] **Lunch Lull** (12:00-1:00 PM): Should show reduced but persistent flow
- [ ] **Power Hour** (3:00-4:00 PM): Should show amplified flow activity
- [ ] **After Hours** (4:00+ PM): Should maintain final flow values

##### Symbol Tests:
- [ ] **SPX/SPXW**: Test 10-point strike increments
- [ ] **SPY**: Test 1-point increments with high liquidity
- [ ] **QQQ**: Test 1-point increments, tech sector flow
- [ ] **Low Volume Stock**: Test behavior with sparse options data
- [ ] **High IV Stock**: Test during earnings/events

##### Edge Case Tests:
- [ ] **Weekend/Holiday**: No data available
- [ ] **Market Gap**: Large overnight moves
- [ ] **Halted Stock**: No new data incoming
- [ ] **Symbol Change**: Ticker modifications
- [ ] **Extreme Volatility**: 5%+ intraday moves

#### ✅ Final Validation Checkpoint:
- [ ] **All market conditions handled gracefully**
- [ ] **No errors in any symbol tested**
- [ ] **Flow direction correlates with obvious market sentiment**
- [ ] **Performance remains acceptable under all conditions**
- [ ] **Data accuracy verified against external sources when possible**

**📈 Accuracy Benchmark**: Compare flow signals to major market events (Fed announcements, earnings reactions, etc.)

---

## 🚨 ROLLBACK PROCEDURES

### If Any Validation Fails:
1. **Document the specific failure mode**
2. **Revert to last working checkpoint**  
3. **Analyze root cause before attempting fix**
4. **Re-run ALL previous validations after fix**
5. **Update CLAUDE.md with lessons learned**

### Performance Degradation Protocol:
- **>5 second load time**: Reduce strike range or optimize calculations
- **>40 requests used**: Review request efficiency, consolidate where possible
- **Memory issues**: Review array management, implement cleanup functions

---

## 📊 SUCCESS METRICS (Before Phase 4)

### Technical Metrics:
- [ ] **<2 second initial load time**
- [ ] **<38 of 40 TradingView requests used**  
- [ ] **>90% uptime during market hours**
- [ ] **<5% calculation errors across all symbols**

### Functional Metrics:
- [ ] **Flow direction correlates with major market moves**
- [ ] **Cumulative flow resets properly at session boundaries**
- [ ] **All 19 strikes contribute meaningful data**
- [ ] **System stable across multiple days of operation**

**🏆 ONLY PROCEED TO PHASE 4 (Advanced Features) AFTER ALL SUCCESS METRICS ACHIEVED**

---

*"Measure twice, cut once. Build it right the first time."*

### File Dependencies & References

#### From Options_volume_main_current.pine copy:
- **Lines 196-214**: Core variable setup and auto-detection
- **Lines 1287-1445**: Strike building and array management  
- **Lines 1534-1678**: Volume fetching and delta calculations
- **Lines 1682-1702**: Volume analysis and POC/Value Area logic

#### From Dynamic_Price_flow.ts.txt:
- **Lines 62-63**: Regular market hours definition
- **Lines 126-135**: Sentiment state persistence logic
- **Lines 164-175**: End-of-session labeling and percentage calculations

#### New Code to Write:
- **Distance weighting algorithm** (custom implementation)
- **Cumulative flow tracking** (session-based reset logic)  
- **Divergence detection engine** (price vs flow comparison)
- **Multi-timeframe analysis** (optional Phase 3 feature)

## 🔍 Gemini AI Analysis - Evaluation

### ✅ Excellent Suggestions
1. **Distance-Weighted Volume**: Brilliant - ATM strikes matter most for immediate price action
2. **Three-Layer Visualization**: Net Delta + Total Energy + Gamma Flip is comprehensive
3. **Session Reset Logic**: Essential for 0DTE - each day is fresh
4. **Divergence Focus**: Price vs flow divergences are high-probability setups

### 🤔 Areas for Refinement  
1. **ITM vs OTM Split**: Conceptually sound but may overcomplicate initial version
2. **Institutional vs Retail Classification**: Difficult to determine without bid/ask data
3. **Background Color Complexity**: May reduce chart readability

### 💡 Additional Enhancements
1. **Volume Acceleration**: Rate of change in flow (flow momentum)
2. **Cross-Timeframe Analysis**: 5min flow vs 1min flow alignment  
3. **Expected Move Integration**: Flow relative to options-implied movement
4. **Market Maker Delta Hedging**: Estimate MM buying/selling pressure

## 🔄 **SESSION PERSISTENCE SOLUTIONS**

### **Recommended Approach: Volume Reconstruction**
```pinescript
// Session volume reconstruction function
reconstructSessionFlow(sessionStartTime) =>
    sessionFlow = 0.0
    for barIndex = sessionStartTime to bar_index
        // Query historical volume for each bar
        barFlow = calculateBarFlow(barIndex)
        sessionFlow := sessionFlow + barFlow
    sessionFlow

// Trigger on refresh detection
if na(sessionCumulativeFlow[1]) and not barstate.isfirst
    // Page was refreshed - reconstruct session
    sessionStartBar = getSessionStartBar(hour, minute)
    sessionCumulativeFlow := reconstructSessionFlow(sessionStartBar)
```

### **Alternative: Checkpoint System**
Store flow state every 30 minutes in persistent arrays, resume from last checkpoint.

### **Technical Challenge**
Unlike options volume profile (independent volume data), flow requires **cumulative calculation state** that's vulnerable to refresh.

## 🎮 Trading Application

### 0DTE Entry Signals
- **Bullish**: Flow breaks above zero + positive acceleration + price confirmation
- **Bearish**: Flow breaks below zero + negative acceleration + price confirmation
- **Scalp Setup**: Flow divergence from price at key levels

### Risk Management Integration
- **Strong Flow**: Trend continuation likely (hold positions)  
- **Weak Flow**: Reversal risk high (reduce size)
- **No Flow**: Ranging market (avoid breakout trades)

### Session Management
- **Morning**: Build bias based on flow direction
- **Midday**: Watch for flow shifts vs price action  
- **Power Hour**: Maximum flow sensitivity for final moves

## 📋 Next Steps

### Immediate Actions
1. **Extract Core Functions**: Identify minimal functions needed from Options Volume Profile
2. **Build Prototype**: Create basic flow calculator with 5 strikes (ATM ±2)
3. **Test Framework**: Validate against known market events
4. **Compare Performance**: Benchmark vs ThinkScript synthetic approach

### Success Validation
- **Historical Backtesting**: Does real flow provide better signals than price momentum?
- **Live Testing**: Real-time performance during high-volatility sessions
- **Edge Quantification**: Measurable improvement in trade timing/accuracy

## 🏆 Expected Outcomes

This project has **significant potential** because:

1. **Real Data Advantage**: Actual volume beats price-momentum proxies
2. **0DTE Focus**: Designed specifically for same-day expiration patterns  
3. **Gamma-Weighted Logic**: Recognizes that ATM strikes drive immediate price action
4. **TradingView Platform**: Superior charting/alert ecosystem vs ThinkScript

**Bottom Line**: If executed properly, this could become a **legitimate edge tool** for options traders, providing institutional-quality flow analysis in a retail platform.

---

*"The best time to trade options is when you know where the options flow is going before the market does."*