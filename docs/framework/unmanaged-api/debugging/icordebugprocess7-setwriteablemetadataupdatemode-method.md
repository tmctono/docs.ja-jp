---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
ms.openlocfilehash: 6de75e1e27660ac91bd6320a501db47f3b055fb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212257"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="4111b-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode メソッド</span><span class="sxs-lookup"><span data-stu-id="4111b-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="4111b-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="4111b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4111b-104">デバッガーが、ターゲット プロセス内のメタデータに対するメモリ内更新をどのように処理するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="4111b-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4111b-105">構文</span><span class="sxs-lookup"><span data-stu-id="4111b-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4111b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4111b-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="4111b-107">ターゲットプロセス内のメタデータに対するメモリ内更新をデバッガーに対して表示 () するか、非表示 () するかを指定する[WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md)列挙値です `WriteableMetadataUpdateMode::AlwaysShowUpdates` `WriteableMetadataUpdateMode::LegacyCompatPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="4111b-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4111b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4111b-108">Remarks</span></span>  
 <span data-ttu-id="4111b-109">ターゲット プロセスのメタデータに対する更新は、[編集]、[続行] で行うか、プロファイラー、または <xref:System.Reflection.Emit?displayProperty=nameWithType> で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4111b-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4111b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4111b-110">Requirements</span></span>  
 <span data-ttu-id="4111b-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4111b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4111b-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4111b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4111b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4111b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4111b-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4111b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4111b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4111b-115">See also</span></span>

- [<span data-ttu-id="4111b-116">ICorDebugProcess7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4111b-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="4111b-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4111b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
