local url = "https://raw.githubusercontent.com/seuUsuario/seuRepositorio/main/meuscript.lua"

local HttpService = game:GetService("HttpService")

local success, response = pcall(function()
    return game:HttpGet(url)
end)

if success then
    local func, err = loadstring(response)
    if func then
        func()
    else
        warn("Erro ao carregar script: " .. err)
    end
else
    warn("Erro ao baixar script: " .. tostring(response))
end
