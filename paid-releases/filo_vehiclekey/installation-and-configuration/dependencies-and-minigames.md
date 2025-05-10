# dependencies & minigames

### Dependencies

{% embed url="https://github.com/overextended/ox_lib" fullWidth="false" %}

{% embed url="https://github.com/overextended/oxmysql" fullWidth="false" %}

### MLO Used

{% embed url="https://forum.cfx.re/t/free-locksmith-mlo/5309829" %}

### Minigames

{% embed url="https://github.com/T3development/t3_lockpick" fullWidth="false" %}

{% embed url="https://github.com/EZ-Scripts/ez_electricminigame" fullWidth="false" %}

If you wanna use a different set of minigames edit ./shared/functions.lua

<pre class="language-lua" data-title="filo_vehiclekey/shared/functions.lua"><code class="lang-lua">function Lockpick(isAdvanced)
    local lockpickStr = isAdvanced and 0.75 or 0.5

    if GetResourceState("filo_skills"):find("start") then
        local skills = exports.filo_skills
        if skills:HasLevel("Lockpicking", 2, 4) then
            lockpickStr = lockpickStr + 0.02
        elseif skills:HasLevel("Lockpicking", 4, 6) then
            lockpickStr = lockpickStr + 0.05
        elseif skills:HasLevel("Lockpicking", 6, 8) then
            lockpickStr = lockpickStr + 0.09
        elseif skills:HasLevel("Lockpicking", 8, 10) then
            lockpickStr = lockpickStr + 0.1
        end

    end
    return exports.t3_lockpick:startLockpick(lockpickStr)
end

<strong>function Hotwire()
</strong>    return exports.ez_electricminigame:WiringFix(30)
end

</code></pre>
