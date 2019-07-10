---
title: ICorDebugSymbolProvider2::GetFrameProps メソッド
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 274da030bbbb7c614709b5150f08f37ddf5aaf5a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771164"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="453c6-102">ICorDebugSymbolProvider2::GetFrameProps メソッド</span><span class="sxs-lookup"><span data-stu-id="453c6-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="453c6-103">メソッドのメソッド開始位置を示す相対仮想アドレスと、指定されたコード相対仮想アドレスを持つ親フレームを返します。</span><span class="sxs-lookup"><span data-stu-id="453c6-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="453c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="453c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="453c6-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="453c6-106">[in] コード相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="453c6-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="453c6-107">[out] メソッドの開始相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="453c6-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="453c6-108">[out] フレームの開始相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="453c6-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="453c6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="453c6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="453c6-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="453c6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453c6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="453c6-111">Requirements</span></span>  
 <span data-ttu-id="453c6-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="453c6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453c6-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="453c6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="453c6-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="453c6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="453c6-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453c6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453c6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="453c6-116">See also</span></span>

- [<span data-ttu-id="453c6-117">ICorDebugSymbolProvider2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="453c6-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="453c6-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="453c6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
