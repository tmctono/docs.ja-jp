---
title: ICorProfilerInfo2::GetAppDomainStaticAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 05d8c44655d8670194035c336bd62ae5d53bfec3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862972"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="7df4f-102">ICorProfilerInfo2::GetAppDomainStaticAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="7df4f-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="7df4f-103">指定したアプリケーションドメインのスコープ内にある、指定したアプリケーションドメインの静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="7df4f-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7df4f-104">構文</span><span class="sxs-lookup"><span data-stu-id="7df4f-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7df4f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7df4f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7df4f-106">から要求されたアプリケーションドメインの静的フィールドを含むクラスのクラス ID。</span><span class="sxs-lookup"><span data-stu-id="7df4f-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="7df4f-107">から要求されたアプリケーションドメインの静的フィールドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="7df4f-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="7df4f-108">から要求された静的フィールドのスコープであるアプリケーションドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="7df4f-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="7df4f-109">入出力指定されたアプリケーションドメイン内の静的フィールドのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7df4f-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7df4f-110">コメント</span><span class="sxs-lookup"><span data-stu-id="7df4f-110">Remarks</span></span>  
 <span data-ttu-id="7df4f-111">`GetAppDomainStaticAddress` メソッドは、次のいずれかを返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="7df4f-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="7df4f-112">指定されたコンテキストで、指定された静的フィールドにアドレスが割り当てられていない場合は CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="7df4f-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="7df4f-113">ガベージコレクションヒープ内に存在する可能性があるオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="7df4f-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="7df4f-114">これらのアドレスは、ガベージコレクションの後に無効になることがあります。そのため、ガベージコレクションの後、プロファイラーはそれらが有効であると想定してはなりません。</span><span class="sxs-lookup"><span data-stu-id="7df4f-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="7df4f-115">クラスのクラスコンストラクターが完了する前に、`GetAppDomainStaticAddress` はすべての静的フィールドに対して CORPROF_E_DATAINCOMPLETE を返します。ただし、静的フィールドの一部は既に初期化されており、ガベージコレクションオブジェクトがルート化される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7df4f-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7df4f-116">要件</span><span class="sxs-lookup"><span data-stu-id="7df4f-116">Requirements</span></span>  
 <span data-ttu-id="7df4f-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7df4f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7df4f-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7df4f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7df4f-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7df4f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7df4f-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7df4f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df4f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7df4f-121">See also</span></span>

- [<span data-ttu-id="7df4f-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7df4f-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7df4f-123">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7df4f-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
