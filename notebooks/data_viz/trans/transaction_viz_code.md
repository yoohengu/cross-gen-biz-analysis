best_month = monthly_price.idxmax()
best_value = monthly_price.max()

print("가장 매출이 높은 달:", best_month)
print("그 달의 매출:", best_value)

plt.figure(figsize=(10,5))
monthly_price.plot()

plt.scatter(best_month.to_timestamp(), best_value)
plt.text(best_month.to_timestamp(), best_value, 
         f"  BEST: {best_month}", fontsize=10)

plt.title("Monthly Total Sales Price")
plt.xlabel("Month")
plt.ylabel("Total Price")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()


plt.figure(figsize=(10,5))
monthly_sales.plot()
plt.title("Monthly Sales")
plt.xlabel("Month")
plt.ylabel("Sales Count")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()

