# mythic_notify-REMADE-FOR-QB-
mythic_notify remade for the qbcore framework
Installation:
Replace the QBCore.Functions.Notify() function in ./qb-core/client/functions.lua:128 with the function below.

function QBCore.Functions.Notify(text, textype, length)
    if textype == "primary" then textype = "inform" end
    if type(text) == "table" then
        local ttext = text.text or 'Placeholder'
        local caption = text.caption or 'Placeholder'
        local ttype = textype or 'inform'
        local length = length or 5000
        exports['mythic_notify']:DoCustomHudText(ttype, ttext, length, caption)
    else
        local ttype = textype or 'inform'
        local length = length or 5000
        exports['mythic_notify']:DoCustomHudText(ttype, text, length)
    end
end

