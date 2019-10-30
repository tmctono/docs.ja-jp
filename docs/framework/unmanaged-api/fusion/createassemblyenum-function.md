---
title: CreateAssemblyEnum 関数
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
ms.openlocfilehash: 0e54027806cef07fad4740c3bf5226fd26c72570
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108774"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="b6e19-102">CreateAssemblyEnum 関数</span><span class="sxs-lookup"><span data-stu-id="b6e19-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="b6e19-103">指定された[IAssemblyName](iassemblyname-interface.md)を持つアセンブリ内のオブジェクトを列挙できる[iassemblyenum](iassemblyenum-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6e19-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e19-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6e19-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6e19-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6e19-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="b6e19-106">入出力要求された `IAssemblyEnum` ポインターを格納しているメモリ位置へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b6e19-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="b6e19-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="b6e19-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b6e19-108">`pUnkReserved` は null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e19-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="b6e19-109">から要求されたアセンブリの `IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="b6e19-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="b6e19-110">この名前は、列挙をフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6e19-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="b6e19-111">グローバルアセンブリキャッシュ内のすべてのアセンブリを列挙するには null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6e19-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b6e19-112">から列挙子の動作を変更するためのフラグ。</span><span class="sxs-lookup"><span data-stu-id="b6e19-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="b6e19-113">このパラメーターには、 [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)列挙体とのビットが1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6e19-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b6e19-114">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="b6e19-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b6e19-115">`pvReserved` は null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e19-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6e19-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6e19-116">Remarks</span></span>  
 <span data-ttu-id="b6e19-117">`dwFlags` パラメーターには、`ASM_CACHE_FLAGS` 列挙体とは1ビットだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6e19-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6e19-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="b6e19-118">Requirements</span></span>  
 <span data-ttu-id="b6e19-119">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e19-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6e19-120">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b6e19-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b6e19-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b6e19-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6e19-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e19-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e19-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6e19-123">See also</span></span>

- [<span data-ttu-id="b6e19-124">IAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6e19-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="b6e19-125">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6e19-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="b6e19-126">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="b6e19-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
