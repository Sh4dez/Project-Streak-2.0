# Project-Streak-2.0
Movement / movement sound
Shooting


void Shoot()

            {
    muzzleFlash.Play();
    
            RaycastHit hit;
             if (Physics.Raycast(fpsCam.transform.position, fpsCam.transform.forward, out hit, range))
    {
               Debug.Log(hit.transform.name);

             Target target = hit.transform.GetComponent<Target>();
             if (target != null)
        {
            target.TakeDamage(damage);
        }
    }




            if (m_CharacterController.velocity.sqrMagnitude > 0 && (m_Input.x != 0 || m_Input.y != 0))
            {
                m_StepCycle += (m_CharacterController.velocity.magnitude + (speed*(m_IsWalking ? 1f : m_RunstepLenghten)))*
                             Time.fixedDeltaTime;
            }

            if (!(m_StepCycle > m_NextStep))
            {
                return;
            }

            m_NextStep = m_StepCycle + m_StepInterval;

            PlayFootStepAudio();
