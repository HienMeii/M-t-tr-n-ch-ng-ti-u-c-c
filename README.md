import pandas as pd

# Tạo DataFrame với dữ liệu từ thực đơn và chi phí hàng tuần
data = {
    'Ngày': list(range(1, 8)),
    'Bữa sáng': [1440, 3000, 2900, 3000, 1440, 3000, 2900],
    'Bữa trưa': [6800, 5470, 7445, 6500, 8714, 3900, 7610],
    'Bữa tối': [33100, 37500, 33850, 32500, 34800, 34000, 33800],
    'Bữa phụ': [1500, 6000, 6000, 6000, 1500, 6000, 6000],
    'Tổng chi phí': [68640, 54700, 74450, 65000, 87140, 39000, 76100]
}

# Tạo DataFrame từ dict
df = pd.DataFrame(data)

# Tạo một writer để ghi DataFrame vào file Excel
writer = pd.ExcelWriter('Thực_đơn_và_Chi_phí.xlsx', engine='xlsxwriter')

# Ghi DataFrame vào file Excel
df.to_excel(writer, index=False)

# Đóng writer
writer.save()

print("File Excel đã được tạo thành công!")
