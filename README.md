$fid = $message->from->id;
$get = bot('getchatmember',[
'chat_id'=>"Bu yerga kanal idi yoziladi",
'user_id'=>$fid
])->result->status;

if(!($get == "creator" or $get == "administrator" or $get == "member")){
bot('sendMessage',[
'chat_id'=>$cid,
'text'=>"Kechirasiz siz bizning @InsofsizGulim kanalimizga a'zo bo'lmagan ekansiz. A'zo bo'lmasangiz botimiz ishlamaydi. A'zo bo'lib qayta /start bosing",
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"A'zo bo'lish",'url'=>"https://t.me/insofsizGulim"]]
]
])
]);
return false;
}
