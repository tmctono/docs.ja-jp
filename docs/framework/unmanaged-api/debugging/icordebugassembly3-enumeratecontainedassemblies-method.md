---
title: ICorDebugAssembly3::EnumerateContainedAssemblies メソッド
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080957"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="cbc4e-102">ICorDebugAssembly3::EnumerateContainedAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="cbc4e-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="cbc4e-103">このアセンブリに含まれているアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbc4e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbc4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbc4e-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="cbc4e-106">[out]列挙子である ICorDebugAssemblyEnum インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbc4e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="cbc4e-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="cbc4e-108">この場合`ICorDebugAssembly3`オブジェクトは、コンテナー、それ以外の`S_FALSE`、列挙子は空です。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-108">if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbc4e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbc4e-109">Remarks</span></span>  
 <span data-ttu-id="cbc4e-110">含まれているアセンブリを列挙するためにシンボルが必要です。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="cbc4e-111">シンボルがない場合、メソッドは `S_FALSE` を返し、有効な列挙子は提供されません。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbc4e-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbc4e-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbc4e-113">Requirements</span></span>  
 <span data-ttu-id="cbc4e-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbc4e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc4e-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbc4e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbc4e-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbc4e-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cbc4e-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cbc4e-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbc4e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbc4e-118">See also</span></span>

- [<span data-ttu-id="cbc4e-119">ICorDebugAssembly3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbc4e-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="cbc4e-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbc4e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
