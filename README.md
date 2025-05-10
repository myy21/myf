# 添加滚动条
        scrollbar = ttk.Scrollbar(center_frame, orient="vertical", command=self.tree.yview)
        self.tree.configure(yscrollcommand=scrollbar.set)
        scrollbar.pack(side="right", fill="y")
        self.tree.pack(fill="both", expand=True)
        
        # 添加双击事件
        self.tree.bind("<Double-1>", self.on_task_double_click)
        
        # 底部框架 - 操作按钮
        bottom_frame = ttk.Frame(self.root)
        bottom_frame.pack(pady=10, padx=10, fill="x")
        
        # 完成按钮
        complete_btn = ttk.Button(
            bottom_frame, 
            text="标记为完成", 
            command=self.mark_task_complete
        )
        complete_btn.pack(side="left", padx=5)
        
        # 删除按钮
        delete_btn = ttk.Button(
            bottom_frame, 
            text="删除任务", 
            command=self.delete_task
        )
        delete_btn.pack(side="left", padx=5)
        
        # 刷新按钮
        refresh_btn = ttk.Button(
            bottom_frame, 
            text="刷新列表", 
            command=self.refresh_task_list
        )
        refresh_btn.pack(side="left", padx=5)
