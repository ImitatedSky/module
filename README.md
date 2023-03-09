# module

device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')

1.保存整個模型
torch.save(model,"save.pt")
載入
mymodel = torch.load('save.pt', map_location=torch.device(device))


2.只保存訓練完的權重
torch.save(model.state_dict(),"save.pt")
model.load_state_dict(torch.load('save.pt', map_location=device))
