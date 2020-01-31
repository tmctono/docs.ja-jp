---
title: ICorDebugMergedAssemblyRecord::GetPublicKey メソッド
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: c8c6e9adcb9d29f5e234dd1b8dfd351fac575301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793117"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="eaba9-102">ICorDebugMergedAssemblyRecord::GetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="eaba9-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="eaba9-103">アセンブリの公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="eaba9-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaba9-104">構文</span><span class="sxs-lookup"><span data-stu-id="eaba9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaba9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eaba9-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="eaba9-106">[in] `pbPublicKey` 配列の最大バイト数。</span><span class="sxs-lookup"><span data-stu-id="eaba9-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="eaba9-107">[out] `pbPublicKey` 配列への実際の書き込みバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="eaba9-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="eaba9-108">[out] アセンブリの公開キーを含むバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="eaba9-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaba9-109">コメント</span><span class="sxs-lookup"><span data-stu-id="eaba9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eaba9-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="eaba9-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaba9-111">要件</span><span class="sxs-lookup"><span data-stu-id="eaba9-111">Requirements</span></span>  
 <span data-ttu-id="eaba9-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaba9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaba9-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eaba9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaba9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaba9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaba9-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaba9-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaba9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaba9-116">See also</span></span>

- [<span data-ttu-id="eaba9-117">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaba9-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="eaba9-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaba9-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
