---
title: ICorDebugMergedAssemblyRecord::GetSimpleName メソッド
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: f6c6682c8bb23143d308aa4f1a6887b28ea82fcd
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209709"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="c30f2-102">ICorDebugMergedAssemblyRecord::GetSimpleName メソッド</span><span class="sxs-lookup"><span data-stu-id="c30f2-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="c30f2-103">アセンブリの簡易名を取得します。</span><span class="sxs-lookup"><span data-stu-id="c30f2-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c30f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c30f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c30f2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c30f2-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="c30f2-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c30f2-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c30f2-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c30f2-108">文字配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c30f2-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c30f2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c30f2-109">Remarks</span></span>  
 <span data-ttu-id="c30f2-110">このメソッドは、アセンブリの簡易名 ("System.Collections" など) を取得します。簡易名には、ファイル拡張子、バージョン、カルチャ、公開キー トークンが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="c30f2-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="c30f2-111">これはマネージド コード内の <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="c30f2-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c30f2-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c30f2-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c30f2-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c30f2-113">Requirements</span></span>  
 <span data-ttu-id="c30f2-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c30f2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c30f2-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c30f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c30f2-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c30f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c30f2-117">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c30f2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30f2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c30f2-118">See also</span></span>

- [<span data-ttu-id="c30f2-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c30f2-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c30f2-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c30f2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
