---
title: ILCodeKind 列挙型
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: b9d27c3e3cd42039aeefcb517ecc81eadeb5c183
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557425"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="5397d-102">ILCodeKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="5397d-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="5397d-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="5397d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5397d-104">デバッガーがローカル変数またはプロファイラー ReJIT インストルメンテーションに追加されたコードにアクセスできるかどうかを指定する値を提供します。</span><span class="sxs-lookup"><span data-stu-id="5397d-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5397d-105">構文</span><span class="sxs-lookup"><span data-stu-id="5397d-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="5397d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5397d-106">Members</span></span>  
  
|<span data-ttu-id="5397d-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="5397d-107">Member name</span></span>|<span data-ttu-id="5397d-108">説明</span><span class="sxs-lookup"><span data-stu-id="5397d-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="5397d-109">デバッガーは、ReJIT インストルメンテーションからの情報に対してアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5397d-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="5397d-110">デバッガーは、ReJIT インストルメンテーションからの情報に対してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5397d-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5397d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5397d-111">Remarks</span></span>  
 <span data-ttu-id="5397d-112">列挙体のメンバーを `ILCodeKind` [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) メソッドおよび [getlocalvariables ex](icordebugilframe4-getlocalvariableex-method.md) メソッドに渡して、デバッガーがプロファイラー rejit インストルメンテーションに追加された変数にアクセスできるかどうかを判断し、 [getcodeex](icordebugilframe4-getcodeex-method.md) メソッドに渡して、デバッガーがインストルメント化された IL にアクセスできるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="5397d-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5397d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5397d-113">Requirements</span></span>  
 <span data-ttu-id="5397d-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5397d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5397d-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5397d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5397d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5397d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5397d-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5397d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5397d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5397d-118">See also</span></span>

- [<span data-ttu-id="5397d-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="5397d-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="5397d-120">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5397d-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="5397d-121">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="5397d-121">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
