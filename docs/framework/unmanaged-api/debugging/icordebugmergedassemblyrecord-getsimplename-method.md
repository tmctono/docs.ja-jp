---
title: ICorDebugMergedAssemblyRecord::GetSimpleName メソッド
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 99ba27171e129e8725c3e0555a6991ef08b893da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178712"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="83424-102">ICorDebugMergedAssemblyRecord::GetSimpleName メソッド</span><span class="sxs-lookup"><span data-stu-id="83424-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="83424-103">アセンブリの簡易名を取得します。</span><span class="sxs-lookup"><span data-stu-id="83424-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83424-104">構文</span><span class="sxs-lookup"><span data-stu-id="83424-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83424-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83424-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="83424-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="83424-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="83424-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="83424-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="83424-108">文字配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="83424-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83424-109">解説</span><span class="sxs-lookup"><span data-stu-id="83424-109">Remarks</span></span>  
 <span data-ttu-id="83424-110">このメソッドは、アセンブリの簡易名 ("System.Collections" など) を取得します。簡易名には、ファイル拡張子、バージョン、カルチャ、公開キー トークンが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="83424-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="83424-111">これはマネージド コード内の <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="83424-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83424-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="83424-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83424-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="83424-113">Requirements</span></span>  
 <span data-ttu-id="83424-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83424-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83424-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83424-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83424-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83424-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83424-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83424-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83424-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="83424-118">See also</span></span>

- [<span data-ttu-id="83424-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83424-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="83424-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83424-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
