-- 導入 "js" 模組local js = require "js"-- global 就是 javascript 的 windowlocal global = js.globallocal document = global.document-- html 檔案中 canvas　id 設為 "canvas"local canvas = document:getElementById("canvas")-- 將 ctx 設為 canvas 2d 繪圖畫布變數local ctx = canvas:getContext("2d")
-- 屬性呼叫使用 . 而方法呼叫使用 :-- 設定填圖顏色ctx.fillStyle = "rgb(0,0,150)"-- 設定畫筆顏色ctx.strokeStyle = "rgb(0,0,150)"

-- 乘上 deg 可轉為徑度單位deg = math.pi / 180
-- 建立多邊形定點位置畫線函式function star(radius, xc, yc, n)    --radius = 100    --xc = 200    --yc = 200    xi = xc + radius*math.cos((360/n)*deg+0*deg)    yi = yc - radius*math.sin((360/n)*deg+0*deg)    ctx:beginPath()    ctx:moveTo(xi,yi)    for i = 2, n+1 do        x = xc + radius*math.cos((360/n)*deg*i+0*deg)        y = yc - radius*math.sin((360/n)*deg*i+0*deg)        ctx:lineTo(x,y)    endendstar(100, 200, 200,6)ctx:closePath()ctx:stroke()ctx:fill()
star(60, 200, 200,6)ctx:closePath()ctx:stroke()ctx.fillStyle = '#fff'ctx:fill()
star(40, 201, 202,1000)ctx:closePath()ctx:stroke()ctx.fillStyle = "rgb(0,0,150)"ctx:fill()--藍色六邊形star(150, 201, 26,6)ctx:closePath()ctx.fillStyle = '#fff'ctx:fill()ctx.strokeStyle = '#fff'
star(15, 200, 200,4)ctx:closePath()ctx.fillStyle =  '#fff'ctx:fill()
star(15, 190, 190,4)ctx:closePath()ctx.fillStyle =  '#fff'ctx:fill()
star(15, 180, 180,4)ctx:closePath()ctx.fillStyle =  '#fff'ctx:fill()
