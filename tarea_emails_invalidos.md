#Tarea emails inválidos

##Script para creacióon de tabla
 '''ql
create table SuperHero(
superhero_id numeric(6,0) constraint pk_superhero primary key,
nombre varchar(250) not null,
email varchar(250) not null
);
create sequence superhero_id_superhero_seq start 1 increment 1;
alter table superhero alter column superhero_id set default nextval('superhero_id_superhero_seq')

'''
>Hola :3>
''' sql
insert into superhero 
(nombre, email)
values('Wanda Maximoff', 'wanda.maximoff@avengers.org'),
('Pietro Maximoff', 'pietro@mail.sokovia.ru'),
('Erik Lensherr', 'fuck_you_charles@brotherhood.of.evil.mutants.space'),
('Charles Xavier', 'i.am.secretely.filled.with.hubris@xavier-school-4-gifted-youngste.'),
('Anthony Edward Stark', 'iamironman@avengers.gov'),
('Steve Rogers', 'americas_ass@anti_avengers'),
('The Vision', 'vis@westview.sword.gov'),
('Clint Barton', 'bul@lse.ye'),
('Natasja Romanov',	'blackwidow@kgb.ru'),
('Thor', 'god_of_thunder-^_^@royalty.asgard.gov'),
('Logan', 'wolverine@cyclops_is_a_jerk.com'),
('Ororo Monroe', 'ororo@weather.co'),
('Scott Summers', 'o@x'),
('Nathan Summers', 'cable@xfact.or'),
('Groot', 'iamgroot@asgardiansofthegalaxyledbythor.quillsux'),
('Nebula', 'idonthaveelektras@complex.thanos'),
('Gamora', 'thefiercestwomaninthegalaxy@thanos.'),
('Rocket', 'shhhhhhhh@darknet.ru')
´´´

<Hola de nuevo>

''' sql

select email as email_invalido
from superhero s 
where email not like '%_@__%.__%'
'''
