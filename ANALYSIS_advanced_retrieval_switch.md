# Analysis: advanced_retrieval_switch Configuration Parameter

## 任务 (Task)
分析advanced_retrieval_switch这个配置参数是在哪次提交中编写到代码中的

Analyze in which commit the `advanced_retrieval_switch` configuration parameter was added to the codebase.

## 分析方法 (Analysis Method)

本次分析使用了以下方法来追踪配置参数：

1. **代码库全文搜索** - 在所有源代码文件中搜索该参数
2. **Git历史搜索** - 使用 `git log -S` 搜索添加/删除该参数的提交
3. **相关配置搜索** - 搜索相关的检索(retrieval)和高级(advanced)配置
4. **文件系统搜索** - 检查配置文件和相关模块

## 分析结果 (Analysis Results)

### 1. 当前代码库状态 (Current Codebase Status)

通过以下命令进行的全面搜索：

```bash
# 搜索所有Go、TypeScript、JavaScript和JSON文件
grep -r "advanced_retrieval_switch" --include="*.go" --include="*.ts" --include="*.tsx" --include="*.js" --include="*.jsx" --include="*.json"

# 结果：未找到任何匹配项
```

**结论**: `advanced_retrieval_switch` 参数在当前代码库中**不存在**。

### 2. Git历史分析 (Git History Analysis)

使用Git pickaxe功能搜索历史：

```bash
# 搜索所有历史提交中添加或删除该参数的记录
git log --all --source --full-history -S"advanced_retrieval_switch" --pretty=format:"%H %ai %an %s"

# 结果：未找到任何匹配的提交
```

代码库提交历史：
- 总提交数：2
- 最早提交：ea7f4107a68d2c1ad065f1646e2f7cd38d5c8ec7 (2025-11-07)
- 最新提交：4e4bfc86e8236e6734b522cb959a9abc7247265e (2025-11-18)

**结论**: 在整个Git历史中**从未添加过** `advanced_retrieval_switch` 参数。

### 3. 相关配置搜索 (Related Configuration Search)

搜索可能相关的retrieval配置：

#### 检索相关文件 (Retrieval-related Files)
以下文件包含retrieval相关功能：

**后端 (Backend)**:
- `backend/domain/workflow/internal/nodes/knowledge/knowledge_retrieve.go` - 知识检索节点
- `backend/domain/knowledge/service/retrieve.go` - 检索服务
- `backend/domain/agent/singleagent/internal/agentflow/node_tool_knowledge.go` - Agent知识工具节点

**前端 (Frontend)**:
- `frontend/packages/arch/resources/studio-i18n-resource/src/locales/en.json` - 包含检索相关国际化文本

但这些文件中**都不包含** `advanced_retrieval_switch` 参数。

#### 高级设置相关 (Advanced Settings Related)
找到一些包含"advanced"的配置文件：
- Intent节点的高级设置：`frontend/packages/workflow/playground/src/node-registries/intent/components/advanced-setting/`
- 模型配置：`backend/conf/model/model_meta.json`
- 开发者API：`backend/api/model/app/developer_api/developer_api.go`

但这些都与 `advanced_retrieval_switch` 无关。

### 4. 可能的解释 (Possible Explanations)

基于分析，有以下几种可能性：

1. **参数名称可能不同** - 实际使用的参数名可能是：
   - `AdvancedRetrievalSwitch` (驼峰命名)
   - `advanced_retrieval` (简化版本)
   - 其他变体

2. **计划中的功能** - 这可能是一个计划添加但尚未实现的配置参数

3. **已被移除** - 虽然Git历史中没有记录，但如果代码库是从其他地方迁移过来的，可能在迁移前已经移除

4. **不同的代码分支** - 可能存在于其他未推送的本地分支中

## 最终结论 (Final Conclusion)

**`advanced_retrieval_switch` 配置参数在当前的 coze-studio 代码库中不存在，也没有任何Git历史记录显示它曾经被添加过。**

### 建议 (Recommendations)

如果您确实需要找到这个参数：

1. 检查是否参数名称有误
2. 确认是否在其他代码仓库中
3. 检查是否在未推送的本地分支中
4. 联系相关开发人员确认该参数的实际名称和位置

---

**分析时间**: 2025-11-18  
**分析范围**: 完整代码库 + 所有Git历史  
**搜索方法**: 文本搜索 + Git pickaxe + 文件系统扫描
