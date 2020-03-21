---
title: ICorDebugDataTarget2::GetImageFromPointer メソッド
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 3ac1f8ab98583357a3aa622b5032d9ae121ebdf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178915"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="8daa0-102">ICorDebugDataTarget2::GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="8daa0-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="8daa0-103">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="8daa0-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8daa0-104">構文</span><span class="sxs-lookup"><span data-stu-id="8daa0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8daa0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8daa0-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="8daa0-106">モジュール内のアドレスを表す[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)値。</span><span class="sxs-lookup"><span data-stu-id="8daa0-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="8daa0-107">[アウト]モジュールのベース アドレスを表す[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)値。</span><span class="sxs-lookup"><span data-stu-id="8daa0-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="8daa0-108">モジュールのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8daa0-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8daa0-109">解説</span><span class="sxs-lookup"><span data-stu-id="8daa0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8daa0-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8daa0-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8daa0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8daa0-111">Requirements</span></span>  
 <span data-ttu-id="8daa0-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8daa0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8daa0-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8daa0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8daa0-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8daa0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8daa0-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8daa0-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8daa0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8daa0-116">See also</span></span>

- [<span data-ttu-id="8daa0-117">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8daa0-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="8daa0-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8daa0-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
