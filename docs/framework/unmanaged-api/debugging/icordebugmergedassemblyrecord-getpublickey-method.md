---
title: Icordebugmergedassemblyrecord::getpublickey メソッド
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7540a87b007656ad3363576f835a89846d287ed1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752732"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="8035c-102">Icordebugmergedassemblyrecord::getpublickey メソッド</span><span class="sxs-lookup"><span data-stu-id="8035c-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="8035c-103">アセンブリの公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="8035c-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8035c-104">構文</span><span class="sxs-lookup"><span data-stu-id="8035c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8035c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8035c-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="8035c-106">[in] `pbPublicKey` 配列の最大バイト数。</span><span class="sxs-lookup"><span data-stu-id="8035c-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="8035c-107">[out] `pbPublicKey` 配列への実際の書き込みバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8035c-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="8035c-108">[out] アセンブリの公開キーを含むバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8035c-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8035c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8035c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8035c-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8035c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8035c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8035c-111">Requirements</span></span>  
 <span data-ttu-id="8035c-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8035c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8035c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8035c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8035c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8035c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8035c-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8035c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8035c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8035c-116">See also</span></span>

- [<span data-ttu-id="8035c-117">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8035c-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="8035c-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8035c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
