# vRPex Rádio para Tokovoip;
Um script simples de rádio por comando de vRPex para tokovoip.

# Como funciona?
É bem simples, mesmo! Basta um player com a devida permisão dar o comando /radio e voala!

# Como eu adiciono canais?
Basta copiar a função de verificação de permissão em skywalker.lua, depois criar uma nova checagem e export para isso em hansolo.lua.

# Exemplo:
RegisterNetEvent('vrp_radio:onradio')
AddEventHandler('vrp_radio:onradio', function()
  if not emradio then
    emradio = true
    if raD.permissaoNome() then
      exports.tokovoip_script:addPlayerToRadio(1)
      channel = 1
    elseif raD.permissaoNovaExemplo() then
      exports.tokovoip_script:addPlayerToRadio(2)
      channel = 2
    end
  else
    emradio = false
    exports.tokovoip_script:removePlayerFromRadio(1)
    exports.tokovoip_script:removePlayerFromRadio(2)
  end
end)
