---
title: ICorDebugDataTarget2::GetImageFromPointer メソッド
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dab9183075f563f52a4fc982eda5cb172556554
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154376"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="6c7b1-102">ICorDebugDataTarget2::GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="6c7b1-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="6c7b1-103">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c7b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="6c7b1-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c7b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c7b1-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="6c7b1-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)モジュール内のアドレスを表す値です。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="6c7b1-107">[out]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)モジュールのベース アドレスを表す値です。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="6c7b1-108">モジュールのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c7b1-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c7b1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c7b1-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c7b1-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6c7b1-111">Requirements</span></span>  
 <span data-ttu-id="6c7b1-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c7b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c7b1-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c7b1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c7b1-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c7b1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6c7b1-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6c7b1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c7b1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c7b1-116">See also</span></span>

- [<span data-ttu-id="6c7b1-117">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c7b1-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6c7b1-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c7b1-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
